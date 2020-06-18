# HOME: Change Main Page Events List

On the main page, `index.html, it displays eight upcomming events.  
The event list on Main page **maintained separatly with *NEWS & EVENT*'s list**, therefore, you need to edit separated event list.  

- Home Events List can be found at `/_data/home_events.yml`
- Each event will use one entry
  - Template
    ```
    - event_name: # upto 35 character
      detail_url: # where detailed description located
      date: # Mmm. DD. YYYY
      location: # upto 35 char
      additional_info1: # 1st line of additional information. 40 character per line
      additional_info2: # 2st line of additional information.
      additional_info3: # 2st line of additional information.
    ```
- Just put new events on top of the existing list, using the template.
- Top Eight Entries will be shown