---
description: Table that defines the User Group parameters.
seo-description: Table that defines the User Group parameters.
seo-title: Query Queue User Groups
solution: Analytics
title: Query Queue User Groups
topic: Data workbench
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
---

# Query Queue User Groups{#query-queue-user-groups}

Table that defines the User Group parameters.

<table id="table_670A47E25A7A43F0B599BD7ABB173E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Name </p> </td> 
   <td colname="col2"> <p>string </p> </td> 
   <td colname="col3"> <p>A user-defined name of the user group, such as Analysts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Policies </p> </td> 
   <td colname="col2"> <p>vector </p> </td> 
   <td colname="col3"> <p>Specifies a policy type. Right-click to choose Standard Policy or Daily Schedule. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard Policy </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>A Standard Policy ensures that users with a low priority are incrementally moved up the queue and scheduled, even if higher priority users enter the queue. You can add multiple policies of the same type in a group, and their effect is cumulative. 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>Priority Limit:</b> The limit above which the priority is not incremented. The maximum priority value. You can use this value to keep the priorities generated by this policy in a specific range (for instance, so that priorities for some other group of users are always higher, or so they do not rise above the Untouchable Priority. </li> 
     </ul> </p> <p> <b>Standard Policy Increments</b> </p> <p>The increment settings for the Standard Policy increase the priority of a query bunch as time passes. This does not force the bunches to be scheduled, but you can use these settings to prioritize users who have been waiting for a long time. The queued parameters affect queries that are currently queued (such as on hold due to insufficient resources to complete them). The scheduled parameters affect queries that are being answered. The priority of a query rises by the number specified in the appropriate increment and increment interval fields: 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>Queued Increment:</b> Sets the priority increment per update while queued. This setting ensures that low priority users are moved up the scheduling queue. </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>Queued Increment Interval:</b> Sets the number of seconds between updates while queued. </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>Scheduled Increment:</b> Sets the priority increment per update while scheduled. </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>Scheduled Increment Interval:</b> Sets the number of seconds between updates while scheduled. <p> <p>Note:  Setting the increment and interval update rates higher for queued bunches than for scheduled bunches can cause oscillation. (For example, suppose you set the Queued Increment value to 100 and the Scheduled Increment to 0, and set the Queued Increment Interval value to 1 and the Untouchable Priority to be high. If two query bunches come in with a base priority of 0, and there are not enough resources to run both queries at the same time, then one of them is scheduled. After one second, the query that was not scheduled has a priority of 100, and preempts the one that was scheduled. After two more seconds, the one that was preempted now has a priority of 200, and the two switch places again. Neither query finishes, because every two seconds the query that is being computed is preempted so the other query can run.) </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Daily Schedule Policy </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Lets you change the priority at specific times of the day. This schedule is useful for automated clients, such as <span class="wintitle"> Report Server</span>, and when users of the system live in different time zones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Changes </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Right-click to add a scheduled priority change. The Change Time is the time of day at which the change occurs. The format is hour:minutes AM/PM. If AM or PM is not entered, the system uses military time. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Priority Limit </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>The maximum priority value resulting from a change. The Priority Change is the amount added to the priority. For example, a value of 0 returns to a default priority. Any other value results in a priority of the default priority plus this number. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Users </p> </td> 
   <td colname="col2"> <p>vector </p> </td> 
   <td colname="col3"> <p>Lists the users that are members of the group. </p> <p> <b>Name:</b> The user’s name as it appears in the Common Name field in the user’s certificate. </p> <p> <b>Extra Priority:</b> Provides additional priority to the user group’s base priority to determine the starting priority for that user. </p> </td> 
  </tr> 
 </tbody> 
</table>

