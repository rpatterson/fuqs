=====================================
fuqs
=====================================
File-based Uncomplicated Queue System
-------------------------------------

A simple queue system that manages and tracks queue activity using
human-readable files on the file-system.  It is intended for use where easy
introspection and ad hoc manipulation of the queues using common tools is more
valuable than volume, throughput, or efficiency; such as personal or hobbyist
projects:

- Queue items are represented by shell/batch script files whose execution
  represents processing the item.

- Items are assigned to different queues by appending the queue name to each
  item's filename before the extension.

- Queue processors claim queue items by renaming the queue item file and
  appending the claimed flag before the extension.  Thus multiple queue
  processors are supported in as much as file renames on the underlying are
  atomic.

- Queue item handling and processing is logged per-item in a log file next to
  the item's file without the queue name so that item history can be followed
  from queue to queue.

- While a queue item is being processed, it's execution PID is written to a
  file next to the item's file to support ad hoc management of queue
  processing.

- Queue workflows are managed by processing one item then renaming that item's
  file to the next queue name and writing it's next processing execution
  commands to that shell/batch script.

- Though not strictly the queue system's job, common queue item processing
  conveniences, such as removing item source files on successful execution,
  are also provided.
