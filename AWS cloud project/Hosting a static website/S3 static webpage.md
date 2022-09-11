# Using Amazon’s unlimited simple storage service (S3) to host a static website where individual web pages include static content.
S3 is an easy-to-use, scalable, and affordable storage service from Amazon. You can use S3 to store any amount of data for a wide range of use cases. Static website hosting, data archival, and software delivery are a few general scenarios where S3 would be a perfect tool
S3 a storage service use to store unlimited data. 
Bucket: This is what i will describe as a father folder, it can consist folders and files. In S3, files are stored in buckets, they are similar to folders on your computer. Every bucket has its own unique name which can be used only once. 
For example, if there is a bucket called “Onecyberthingaday”, neither you nor anyone else can re-use the same bucket name. Now lets get our hands dirty.

## `Hosting a static website`
## `Create a bucket`

Static website is an informational site, any website you don't have to log into before you can access content. it retains the same info for everyone that visit e.g blog sites. S3 can be used to host a static website

Download a source code you want from here: https://startbootstrap.com or Google drive link: https://drive.google.com/drive/folders/

    search and click  "S3" from management console
    CLick on "Create bucket"
![image not found](images/cfbucket01.png)

    Fill in the general configuration.Bucket name must be unique.
![image not found](images/cfbucket.png)

    Uncheck block public access (Not recommended)
    Enable encryption (it is a best practice)
    Enable bucket version
![image not found](images/cfbucket3.png)

    Proceed to "create bucket"
![image not found](images/cfbucketsuccess.png)

## `Upload source code`
Now we will procced to upload the source code we downloaded earlier into the bucket we just created.

    Select your newly created bucket, click upload
![image not found](images/codeupload1.png)

    Drag and drop all downloaded file or upload the folder
    click on "upload"
![image not found](images/codeupload2.png)

    Wait for folder to upload and click close.
![image not found](images/codeupload3.png)
![image not found](images/codeupload4.png)

## `Enable static Website Hosting`
    Go back to the bucket and click on properties tab.
    Scroll to the extreme end and locate static website. click on "Edit"
    select "enable" for static website hosting
    ensure host a static website is checked from drop down
    Type in your index document i.e homepage. it is an html extension.
    if the site have an error page, add it to the error document 
    click "save changes"
![image not found](images/staticwebhost.png)

You should see the link to your website now. Let me guess, you clicked the link and got an error mesaasge right? Don't worry it is a security measure, now lets troubleshoot that.
![image not found](images/staticwebhost2.png)

##  Give public access
    Click on the "permissions tab". locate bucket policy and click edit.
![image not found](images/staticwebhost3.png)

    Paste your copied policy on policy page and save.
    Remember to replace aws:s3:::DOC-EXAMPLE-BUCKET with your bucket ARN.
    {
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicRead",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject",
                "s3:GetObjectVersion"
            ],
            "Resource": [
                "arn:aws:s3:::DOC-EXAMPLE-BUCKET/*"
            ]
        }
    ]
    }

![image not found](images/staticwebhost4.png)

    refresh your webpage and viola...
![image not found](images/staticwebhost5.png)


# `S3 Versioning`
Allows you have multiple version of a file so you can always recover the file. when a file is deleted in a bucket a delete marker will be placed on it in a version view.
    Follow steps above to create a static website, ensure to enable bucket versioning. upload a text file.
    edit the uploaded file and upload again to override the former file

To view  the new uploaded file, `make the object public`

    locate enable object ownership and select "ACLs enabled"
![image not found](images/enableACL.png)


**Additional resources**

Google search Read-only permission for annonymous users. copy the policy.

https://www.youtube.com/watch?v=I-Y0yG27zAM&list=PL3F_GLbU0tgo9WUas0tN5DD9h5aQjFJ_p&index=4
https://docs.aws.amazon.com/AmazonS3/latest/userguide/example-bucket-policies.html#example-bucket-policies-use-case-2
https://docs.aws.amazon.com/AmazonS3/latest/userguide/example-bucket-policies.html