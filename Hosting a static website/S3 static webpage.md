S3 is an easy-to-use, scalable, and cheap storage service from Amazon. You can use S3 to store any amount of data for a wide range of use cases. Static website hosting, data archival, and software delivery are a few general scenarios where S3 would be a perfect tool
S3 a storage service use to store unlimited data. 
bucket is a father folder, it can consist folders and files. In S3, files are stored in buckets. Buckets are similar to folders on your computer.Every bucket has its own unique name which can be used only once. 
For example, if there is a bucket called “Onecyberthingaday”, neither you nor anyone else can re-use the same bucket name

## Hosting a static website

Static website is an informational site, any website you don't have to log into befire you can access content. it retains the same info for everyone that visit e.g blog sites. S3 can be used to host a static website

Download a source code you want from here: https://startbootstrap.com or Google drive link: https://drive.google.com/drive/folders/

    "search and click Amazon S3" from management console
    CLick on "Create bucket"

    Fill in the general configuration note that bucket name must be unique.
    Uncheck block public access (Not recommended for )
    Enable encryption (it is a best practice)
    Enable bucket version

    Proceed to "create bucket"
## Upload source code
Now we will procced to upload the source code we downloaded earlier into the bucket we just create.
    Select your newly created bucket, click upload
    Drag and drop all downloaded file or upload the folder
    click on "upload"
Wait for folder to upload and click close.
## Enable static Website Hosting
Go back to the bucket and click on properties tab.
Scroll to the extreme end and locate static website. click on "Edit"

select "enable" for static website hosting
ensure host a static website is checked from drop down
After uploading your folder locate static website.
Type in your index document i.e homepage. it is an html extension.
if the site have an error page, add it to the error document 
click "save changes"
You should see the link to your website now. Let me guess, you clicked the link and got an error mesaasge right? Don't worry it is a security measure, now lets troubleshoot that.

##  Give public access
Click on the "permissions tab". locate bucket policy and click edit.
Paste on policy page
**note:** replace name in resource with your bucket ARN.
click save

refresh your webpage and viola...

note: 
Google search Read-only permission for annonymous users. copy the policy.

Additional resources: 
https://www.youtube.com/watch?v=I-Y0yG27zAM&list=PL3F_GLbU0tgo9WUas0tN5DD9h5aQjFJ_p&index=4
https://docs.aws.amazon.com/AmazonS3/latest/userguide/example-bucket-policies.html#example-bucket-policies-use-case-2