# NEWS & EVENT: Add/Change Event/News List

On the NEWS & EVENT, it displays list of events.  
The event list on NEWS & EVENT page **maintained separatly with *HOME*'s list**, therefore, you need to edit separated event list.  

- Events List can be found at `/_data/events.yml`
- Each event will use one entry
  - Template
    ```
    - event_name: # upto 35 character
      detail_url: # where detailed description located
      date: # Mmm. DD. YYYY
      location: # upto 35 char
    ```
    - All entries are required