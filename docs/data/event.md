---
sidebar_position: 4
---

# Events

Information about hackathons and large public events populates the **Events** tab on the Leadership site. 

### Schema

The following information about teams is stored.

```ts
interface event {
  id: string;
  name: string;
  
  date_start?: firestore.Timestamp | string;
  date_end?: firestore.Timestamp | string;
  team?: [officer];
  director?: officer[];
  filter?: string[];
}
```

:::tip
The `id` field for each event can be seen when accessing their profile page as follows --> `https://leadership.acmutd.co/event/<ID>`. This is a uniquely auto-generated id that also serves as the document name in the `event_leadership` collection on firestore.
:::

The `date_start` and `date_end` fields on the document are stored as timestamps in Firestore but are converted to and used as a `string` in the application logic.

### Team

The team array contains an array of officers. For each officer only the `id` and `name` fields are saved. The `name` field is used by the leadership site to display the list of participants in a team. The `id` field is used to redirect to the officer's profile page and by the GraphQL API to access all the participant's properties.

### Filter

The filter array contains the list of possible tags to make searches with. For example the most commonly used filter is `hackathon`. The information in this array is used by the filter functionality on the events tab.

### Aggregations

To avoid having to read all documents when populating the events tab of the leadership site, some information is aggregated into a single document. The following information is stored in the `total/events_leadership` document. 

```ts
interface totalEvent {
    events: event[];
    filter: string[];
}
```

:::caution
Only the **required** fields from the event interface is used to populate the aggregation document. This reduces the size of the document and ensures that only the information required is loaded up.
:::

To accomodate for reading only the aggregation document vs reading all the profile information about an officer, the `event` interface only requires the `id` and `name` fields. The full `event` interface with all fields is read back when loading up the full page. The filter field is set of all possible searches which can be made.