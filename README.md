# Risk-assessment
## Name:Shreenidhi S
## Reg no: 212225040410

## AUDITING CLOUD ACTIVITY USING AWS CLOUDTRAIL
## Objective
To audit and monitor cloud activity in AWS using AWS CloudTrail by viewing and analyzing recorded AWS events and identifying important audit information such as:

1.User identity
2.Event name
3.Event time
4.AWS service
5.Region
6.Operation status
## 1. Requirements
1.AWS Account
2.Web Browser
3.Internet Connection
4.Amazon S3 Access
5.AWS CloudTrail
## PART A — ACCESS AWS CLOUDTRAIL
## Step 1: Login to AWS
1.Open the AWS Management Console.
2.Sign in using your AWS account.
3.In the AWS search bar, type CloudTrail.
4.Select AWS CloudTrail.
Screenshot 1: AWS CloudTrail Dashboard
<img width="1915" height="942" alt="Screenshot 2026-09-06 213632" src="https://github.com/user-attachments/assets/34132a65-e3c5-45ad-a15c-bc0a86d66ae6" />

## Step 2: Open Event History
1.In the CloudTrail navigation menu, select Event history.
2.CloudTrail displays recent AWS activity.
3.Review the available events.
The Event History page may display information such as:

1.Event Time
2.Username
3.Event Name
4.Event Source
5.Resource Type
6.Resource Name

## Screenshot 2: CloudTrail Event History
<img width="1912" height="948" alt="Screenshot 2026-09-05 153930" src="https://github.com/user-attachments/assets/a0115130-f6ad-45c8-99f1-372103c2ed42" />

## PART B — ANALYZE A CLOUDTRAIL EVENT
## Step 3: Select an Event
1.From the Event History list, select an S3-related event.
2.Click the event to open its details.
3.Examine the event information and the event record/JSON.
4.For this experiment, a CreateKeyPair event can be used.

## Step 4: Analyze the CreateKeyPair Event
The CreateKeyPair event indicates that an Amazon EC2 bucket creation operation occurred.

## CreateKeyPair Event Observation
## Meaning of Important Fields
<table border="1">
  <tr>
    <th>Field</th>
    <th>Meaning / Observation</th>
  </tr>

  <tr>
    <td>Event Time</td>
    <td>August 05, 2026, 11:09:16 (UTC+05:30) — Time at which the activity occurred</td>
  </tr>

  <tr>
    <td>User Name</td>
    <td>root — User/identity associated with the activity</td>
  </tr>

  <tr>
    <td>Event Name</td>
    <td>CreateKeyPair — AWS operation that was performed</td>
  </tr>

  <tr>
    <td>Event Source</td>
    <td>CreateKeyPair — AWS service that generated the event</td>
  </tr>

  <tr>
    <td>AWS Region</td>
    <td>ap-south-1 — Region where the activity occurred</td>
  </tr>

  <tr>
    <td>Read-only</td>
    <td>false — The event involved a change/creation operation</td>
  </tr>

  <tr>
    <td>Error Code</td>
    <td>- — No error code was reported</td>
  </tr>
</table>


## Screenshot 3: CreateKeyPair Event Details
<img width="1912" height="890" alt="Screenshot 2026-09-05 203827" src="https://github.com/user-attachments/assets/643457c9-0ad9-48a2-95e7-3ce73ebf6756" />

## PART C — IDENTIFY ANOTHER CLOUDTRAIL EVENT
## Step 5: Select Another Event
1.Return to CloudTrail → Event history.
2.Select another event.
3.Open its details.
4.Record the important fields.
For example, an event such as:
~~~
s3.amazonaws.com
~~~
may be present.

This event is associated with Amazon S3.

## Step 6: Analyze the Second Event

## Screenshot 4: Second CloudTrail Event Details
<img width="1906" height="902" alt="Screenshot 2026-09-05 203908" src="https://github.com/user-attachments/assets/7de5d8d4-33c9-4dac-983c-98a608d8171e" />
## PART D — COMPARE THE EVENTS
## Step 7: Prepare the Audit Comparison
<h3>Compare the two CloudTrail events</h3>

<table border="1" cellpadding="8" cellspacing="0">
  <tr>
    <th>Parameter</th>
    <th>Event 1</th>
    <th>Event 2</th>
  </tr>

  <tr>
    <td>Event Time</td>
    <td>August 05, 2026, 11:09:16 (UTC+05:30)</td>
    <td>September 02, 2026, 10:36:11 (UTC+05:30)</td>
  </tr>

  <tr>
    <td>User Name</td>
    <td>root</td>
    <td>root</td>
  </tr>

  <tr>
    <td>Event Name</td>
    <td>CreateKeyPair</td>
    <td>CreateBucket</td>
  </tr>

  <tr>
    <td>Event Source</td>
    <td>ec2.amazonaws.com</td>
    <td>s3.amazonaws.com</td>
  </tr>

  <tr>
    <td>AWS Region</td>
    <td>eu-north-1</td>
    <td>eu-north-1</td>
  </tr>

  <tr>
    <td>Read-only</td>
    <td>false</td>
    <td>false</td>
  </tr>

  <tr>
    <td>Error Code</td>
    <td>-</td>
    <td>-</td>
  </tr>

  <tr>
    <td>Activity</td>
    <td>EC2 key pair creation</td>
    <td>S3 bucket creation</td>
  </tr>
</table>
---

# PART E — SECURITY AUDIT ANALYSIS


### RESULT?

Was the operation successful or did it generate an error?

---


## Step 8: Prepare the Final Audit Table

The final audit table summarizes the important details of both CloudTrail events:

<table border="1" cellpadding="8" cellspacing="0">
  <tr>
    <th>Event Time</th>
    <th>User</th>
    <th>Event Name</th>
    <th>Service</th>
    <th>Region</th>
    <th>Read-only</th>
    <th>Result</th>
    <th>Activity</th>
  </tr>

  <tr>
    <td>August 05, 2026, 11:09:16 (UTC+05:30)</td>
    <td>root</td>
    <td>CreateKeyPair</td>
    <td>Amazon EC2</td>
    <td>eu-north-1</td>
    <td>false</td>
    <td>Successful</td>
    <td>EC2 key pair creation</td>
  </tr>

  <tr>
    <td>September 02, 2026, 10:36:11 (UTC+05:30) </td>
    <td>root</td>
    <td>CreateBucket</td>
    <td>Amazon S3</td>
    <td>eu-north-1</td>
    <td>false</td>
    <td>Successful</td>
    <td>S3 bucket creation</td>
  </tr>
</table>

# RESULT

The cloud activities in AWS were successfully audited using **AWS CloudTrail Event History**.

Different AWS events were examined based on:

- Event time
- User identity
- Event name
- Event source
- AWS Region
- Read-only status
- Error status

The experiment demonstrated how **AWS CloudTrail** provides an audit trail for monitoring, accountability, and investigation of cloud activities.

