#Compress Image
##Python
- http://wiki.ros.org/ja/rospy_tutorials/Tutorials/WritingImagePublisherSubscriber

##C++
- 情報がなさすぎるのでサンプルをメモしておく。たったコレだけのことなのに…。
```bash
void hogeClass::CompressedImageSubscribe (const sensor_msgs::CompressedImagePtr & compress_img_msg)
{
    cv::Mat decoded_img;
    decoded_img = cv::imdecode(cv::Mat(compress_img_msg->data), 1);
}
```
