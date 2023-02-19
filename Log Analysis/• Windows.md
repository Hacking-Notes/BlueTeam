--- ---

<h2>Log Analysis</h2>

In any Windows system, the Event Viewer, a **Microsoft Management Console (MMC)** snap-in, can be launched by simply right-clicking the Windows icon in the taskbar and selecting **Event Viewer**. For the savvy sysadmins that use the CLI much of their day, Event Viewer can be launched by typing `eventvwr.msc`. It is a GUI-based application that allows you to interact quickly with and analyze logs.

- Event Viewer has three panes.

1.  The pane on the left provides a hierarchical tree listing of the event log providers.
2.  The pane in the middle will display a general overview and summary of the events specific to a selected provider.
3.  The pane on the right is the actions pane.

![[Pasted image 20221203183731.png]]

These events are usually categorised into the following:

![[Pasted image 20221202100956.png]]

---

<h2>Looking Through Log Files</h2>

Log files can quickly contain many events and hundreds, if not thousands, of entries. The difficulty in analysing log files is separating useful information from useless. Tools such as Splunk are software solutions known as Security, and Event Information Management (SIEM) is dedicated to aggregating logs for analysis.

---> [[• Splunk]]
