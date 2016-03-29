# s3Bucket
  You are looking for Amazon S3 bucket file upload from your web. You need to fallow couple of steps get it done :zap:

###### Login to Amazon account and click [here](https://console.aws.amazon.com/iam/home?#security_credential) to get Access Credentials.


###### To create a new Amazon S3 Bucket: (use can also use ctrl+n )
- [x] Click Buckets ->Create New Bucket

  ![alt tag](http://s3browser.com/images/create-s3-bucket/buckets-menu.png)

- [x] Create New Bucket dialog will appear:

  ![alt tag](http://s3browser.com/images/create-s3-bucket/new-bucket-dialog.png)

- [x] Enter unique bucket name (bucket namespace is shared among all buckets from all of the accounts in S3)

- [x] Choose bucket location:
1.    US Standard - Uses Amazon S3 servers in the United States. This is the default Region.
2.    US-West (Northern California) - Uses Amazon S3 servers in Northern California.
3.    US-West (Oregon) - Uses Amazon S3 servers in Oregon.
4.    Europe(Ireland) - Uses Amazon S3 servers in Ireland.
5.    EU (Frankfurt) - Uses Amazon S3 servers in Frankfurt.
6.    Asia Pacific (Singapore) - Uses Amazon S3 servers in Singapore.
7.    Asia Pacific (Japan) - Uses Amazon S3 servers in Tokyo, Japan.
8.    Asia Pacific (Sydney) - Uses Amazon S3 servers in Sydney, Australlia.
9.    Asia Pacific (Seoul) - Uses Amazon S3 servers in Seoul, South Korea.
10.    South America (Sao Paulo) - Uses Amazon S3 servers in Sao Paulo, Brazil.

- [x] Click OK

  New Amazon S3 Bucket will be created. Your new bucket will appear in the list.
  
  ![alt tag](http://s3browser.com/images/create-s3-bucket/new-s3-bucket-created.png)
  
###### Create a bucket and right click select properties, add permission select Everyone enable check list box. 
  ![alt tag](https://lh3.googleusercontent.com/-LIv6GTsqptE/UCAI1PJaY4I/AAAAAAAAGYg/s4oX9dKmM5c/s550/permissions.png)


###### open s3_config.php Here you have to provide amazon key details.
<pre>
// Bucket Name
$bucket="BucketName";
if (!class_exists('S3'))require_once('S3.php');

//AWS access info
if (!defined('awsAccessKey')) define('awsAccessKey', 'ACCESS_KEY');
if (!defined('awsSecretKey')) define('awsSecretKey', 'ACCESS_Secret_KEY');

$s3 = new S3(awsAccessKey, awsSecretKey);
$s3->putBucket($bucket, S3::ACL_PUBLIC_READ);
</pre>

###### use putObjectFile funtion to move your file itno amzon bucket.
<pre>$s3->putObjectFile($tmp, $bucket , $image_name, S3::ACL_PUBLIC_READ)</pre>



