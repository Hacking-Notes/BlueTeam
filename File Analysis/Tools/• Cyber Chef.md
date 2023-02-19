--- ---

<h2>CyberChef Overview</h2>

https://cyberchef.org/

CyberChef is a web-based application - used to slice, dice, encode, decode, parse and analyze data or files. The CyberChef layout is explained below. An offline version of cyberChef is bookmarked in Firefox on the machine attached to this task.  

![CyberChef Interface](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/47c75a03ac04b0c2922a1cbbcefad496.png)

1.  Add the text or file in panel 1.
2.  Panel 2 contains various functions, also known as recipes that we use to encode, decode, parse, search or filter the data.
3.  Drag the functions or recipes from Panel 2 into Panel 3 to create a recipe.
4.  The output from the recipes is shown in panel 4.
5.  Click on bake to run the functions added in Panel 3 in order. We can select AutoBake to automatically run the recipes as they are added.

---

<h2>Using CyberChef for mal doc analysis</h2>

Let's utilize the functions, also known as recipes, from the left panel in CyberChef to analyze the malicious doc. Each step is explained below:  

**1) Add the File to CyberChef**

Drag the invoice.doc file from the desktop to panel 1 as input, as shown below. Alternatively, the user can add the`Division_of_labour-Load_share_plan.doc` file by Open file as input icon in the top-right area of the CyberChef page.  

![Shows how to drag a file into CyberChef as input](https://tryhackme-images.s3.amazonaws.com/user-uploads/62c435d1f4d84a005f5df811/room-content/44901d6b3afd7c63acf7c9c0c9c3e18b.gif)  

**2) Extract strings**  

Strings are ASCII and Unicode-printable sequences of characters within a file. We are interested in the strings embedded in the file that could lead us to suspicious domains. Use the `strings` function from the left panel to extract the strings by dragging it to panel 3 and selecting **All printable chars** as shown below:  

![Extract strings using strings function](https://tryhackme-images.s3.amazonaws.com/user-uploads/62c435d1f4d84a005f5df811/room-content/12b35d2dcb21944881d978f6f65e8d42.gif)  

If we examine the result, we can see some random strings of different lengths and some obfuscated strings. Narrow down the search to show the strings with a larger length. Keep increasing the minimum length until you remove all the noise and are only left with the meaningful string, as shown below:  

![Filter strings by the size using strings function](https://tryhackme-images.s3.amazonaws.com/user-uploads/62c435d1f4d84a005f5df811/room-content/6e8e2cb719260599ed8a51843b34fa19.png)  

**3) Remove Pattern  
**

Attackers often add random characters to obfuscate the actual value. If we examine, we can find some repeated characters `[ _ ]`. As these characters are common in different places, we can use regex **(regular expressions)** within the `Find / Replace` function to find and remove these repeated characters.

To use regex, we will put characters within the square brackets `[ ]` and use backslash `\` to escape characters. In this case, the final regex will be`[**\[\]\n_**]` where `\n` represents **the Line feed**, as shown below:

![Use Regex in Find/Replace to filter data](https://tryhackme-images.s3.amazonaws.com/user-uploads/62c435d1f4d84a005f5df811/room-content/8c0b0f724002e6dc8457d8b7f095c486.png)  

It's evident from the result that we are dealing with a PowerShell script, and it is using base64 Encoded string to hide the actual code.  

**4) Drop Bytes**

To get access to the base64 string, we need to remove the extra bytes from the top. Let's use the `Drop bytes` function and keep increasing the number until the top bytes are removed.

![Use drop bytes to drop unwanted bytes](https://tryhackme-images.s3.amazonaws.com/user-uploads/62c435d1f4d84a005f5df811/room-content/c1e177a5656640e25ef0c5a83990f8a7.png)  

**5) Decode base64**

Now we are only left with the base64 text. We will use the `From base64` function to decode this string, as shown below:

![Use from Base64 to decode text from Base84 encoded value](https://tryhackme-images.s3.amazonaws.com/user-uploads/62c435d1f4d84a005f5df811/room-content/309cbbd50b3b5e27e17677f96f04b069.png)  

**6) Decode UTF-16  
**

The base64 decoded result clearly indicates a PowerShell script which seems like an interesting finding. In general, the PowerShell scripts use the `Unicode UTF-16LE` encoding by default. We will be using the `Decode text` function to decode the result into UTF-16E, as shown below:

![Decode to UTF-16LE using decode text function](https://tryhackme-images.s3.amazonaws.com/user-uploads/62c435d1f4d84a005f5df811/room-content/0faa8f5668d9d998696aa8547d80c3b7.png)  

**7) Find and Remove Common Patterns**

Forensic McBlue observes various repeated characters  ``' ( ) + ' ` "`` within the output, which makes the result a bit messy. Let's use regex in the `Find/Replace` function again to remove these characters, as shown below. The final regex will be ``['()+'"`]``.  

![Use regex within Find/Replace to filter data](https://tryhackme-images.s3.amazonaws.com/user-uploads/62c435d1f4d84a005f5df811/room-content/da469d1dabcf929dbc1765d06917521d.png)  

**8) Find and Replace  
**

If we examine the output, we will find various domains and some weird letters `]b2H_` before each domain reference. A replace function is also found below that seems to replace this `]b2H_` with `http`.

![Shows usage of Find/Replace function](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/938334f69a64ce058bd2046da3928114.png)  

Let's use the `find / Replace` function to replace `]b2H_` with `http` as shown below:

![Use Replace/Replace function to replace chars](https://tryhackme-images.s3.amazonaws.com/user-uploads/62c435d1f4d84a005f5df811/room-content/d71d6682328beec84e0948a6ade15c69.png)  

**9) Extract URLs**

The result clearly shows some domains, which is what we expected to find. We will use the `Extract URLs` function to extract the URLs from the result, as shown below:

![Use Extract URLs function to extract URLs from the data](https://tryhackme-images.s3.amazonaws.com/user-uploads/62c435d1f4d84a005f5df811/room-content/76d6badf89e2022315851487435f12f6.png)  

**10) Split URLs with @**

The result shows that each domain is followed by the `@`character, which can be removed using the split function as shown below:

![Use split function to split lines](https://tryhackme-images.s3.amazonaws.com/user-uploads/62c435d1f4d84a005f5df811/room-content/7f2239c965339cf309d101f6c8d713eb.png)  

**11) Defang URL**  

Great - We have finally extracted the URLs from the malicious document; it looks like the document was indeed malicious and was downloading a malicious program from a suspicious domain.

Before passing these domains to the SOC team for deep malware analysis, it is recommended to defang them to avoid accidental clicks. Defanging the URLs makes them unclickable. We will use `Defang URL` to do the task, as shown below:  

![Use Defang to defang URLs to make them unclickable](https://tryhackme-images.s3.amazonaws.com/user-uploads/62c435d1f4d84a005f5df811/room-content/58a58436becb51b25dbb13ebe56b9a02.png)