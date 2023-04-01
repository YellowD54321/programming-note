[**AWS Lambda**](https://aws.amazon.com/lambda) is a service that lets you run code without needing to provision or manage servers. 

While using AWS Lambda, you pay only for the compute time that you consume. Charges apply only when your code is running. You can also run code for virtually any type of application or backend service, all with zero administration. 

For example, a simple Lambda function might involve automatically resizing uploaded images to the AWS Cloud. In this case, the function triggers when uploading a new image.

### **How AWS Lambda works**

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/aFDLTd29SHSQy03dvZh02w_14639fa7da6e4e7f895ffb6720671934_Lambda.png?expiry=1611446400000&hmac=Pxf2k_gU7iyQWOslI8Y0EjiEzgbD-1eKu_KVL16YC5c)

1.  You upload your code to Lambda. 
    
2.  You set your code to trigger from an event source, such as AWS services, mobile applications, or HTTP endpoints.
    
3.  Lambda runs your code only when triggered.
    
4.  You pay only for the compute time that you use. In the previous example of resizing images, you would pay only for the compute time that you use when uploading new images. Uploading the images triggers Lambda to run code for the image resizing function.