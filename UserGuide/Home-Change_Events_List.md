# HOME: Change Main Page Events List

On the main page, it displays eight upcomming events.  
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
    - `detail_url`, `additional_info1`, `additional_info1`, and `additional_info1` are only used when there exist, otherwise, leave those contents blank.  
      Though there's nothing, the entry needs to exist.
- Just put new events on top of the existing list, using the template.
- Top Eight events will be shown
  - The maximum number of events can be modified [here](https://github.com/hyecheol123/KSEAWeb-Jekyll/blob/master/index.html#L19).