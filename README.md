#Autodesk View and Data API sample using an ASP.NET Webform 


##Description

This is a ASP.NET Webform sample providing functions to :

* Upload a file to a bucket.
* Start the translation of the file.
* Check translation progress.
* Load the translated file into the viewer. 

See the [live demo](http://checkoutmymodel.autodesk.io/).

##Dependencies

This sample uses the [RestSharp](http://restsharp.org/) and [log4net](http://logging.apache.org/log4net/index.html) libraries.  You can add them to your project using NuGet in Visual Studio. 

##Setup/Usage Instructions

* Get your consumer key and secret key from http://developer.autodesk.com.
* Run Visual Studio 2012 or 2013 and open ViewAndShare.sln
* Set the API keys in the Credentials.cs file.
* Change the bucket name for uploading files (also in the Credentials.cs file). The bucket name must match the pattern  “^[-_.a-z0-9]{3,128}$” - i.e. the bucket name must be between 3 to 128 characters long and contain only lowercase letters, numbers and the symbols ._–.  Bucket keys must be unique within the data center or region in which they were created. Therefore, to ensure uniqueness, we recommend you incorporate your company name/domain name or consumer public key (converted to lowercase) into the bucket name.
* Go to property of "ViewAndShare" web project, in "Web" tab, it uses "IIS Express", click "Create Virtual Directory". 
* Please note that you may get "Load Error: 5" error for the first time when you launch the application, this is an expected behaviour. The reason is because a default model urn is hard-coded in the sample for the first run but you don't have access to it with your key pair. Please ignore this error message and upload your models using the 'Upload your files' button. Once you’ve successfully uploaded and translated a model, you can set this as your default model by copying the URN for that model into 'default.aspx', around line 247:

        $(document).ready(function () {

            var g_checkProgress = null;

            var g_urn = Autodesk.Viewing.Private.getParameterByName("urn");

            //default model
            if (!g_urn) {
                g_urn = 'dXJuOmFkc2sub2JqZWN0czpvcy5vYmplY3Q6YnVja2V0X2NoZWNrb3V0bXltb2RlbC9EcmlsbC5kd2Z4';
            }

You can get your model urn by clicking the 'Share' button, the urn is the parameter of sharing URL.
			
## License

This sample is licensed under the terms of the [MIT License](http://opensource.org/licenses/MIT). Please see the [LICENSE](LICENSE) file for full details.

##Written by 

Daniel Du





    
