# create IAM user

IAM is a service in AWS that is used to grant permission to different AWS services.

GOTO services and search IAM

SELECT USERS from the left pane. select add user

set username , select access type
Programmatic access: enable user configure using dev tools such as CLI, SDK AWS API etc
AWS mgt console access: enable user configure using GUI
Console passwored: Autogenerate or custom password
Require password reset: This enable user change their password on dign in

2. set permissions
Select Attach existing policy and select preferred policies as required

Tag: it is use for organizing 

3. Review and create user

IMPORTANT: Download .csv on the next page. This file contain the unique login link of the user created.

# Create groups

Best practise:
Don't logon with email
Don't log on with root user
Put users into groups 