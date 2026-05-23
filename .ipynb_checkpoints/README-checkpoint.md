# Rearc Cybersecurity Detection Quest

## Submission Notes, Sam Wakelam.

### Part 1
- I read in the data and parsed it into a dataframe using a rough schema I built through quick exploration of the log fields.
- Since each eventID had unique fields, I held off parsing all fields until I knew the eventID I would be looking for to avoid excessive null columns.
- This dataframe was only intended for exploration, I acknowledged the need to build a more robust schema when the search became more defined.

### Part 2
- I created a function to parse and build a schema for a given event ID.
- I used this function to create a new silver dataframe with columns tuned to searching DNS logs (eventID 22).
- I used spark sql to query the logs for DNS traffic from windows applications to unexpected destinations, identifying the suspicious event.

### Part 3
- I normalised the data in alignment with the ECS framework by realiasing the dataframe field names.
- I designed a simulation alert table containing data from the identified suspicious event, as well as invented metadata as I would expect an analyst to use in a SIEM.
- I used VirusTotal, AbuseIPDB and Hybrid Analysis to enrich the alert for a prosective analyst.