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

###Matlab on Windows
- kubuntu のturtlebotと繋ぐ
  - kubuntu
    - `gazebo TrutleBot World` を開く。コンソールに色々出てきてgazeboが立ち上がる。
    - `Publicized address: 192.168.183.128` がgazeboっぽい。
  - Windowsマシン
    - ネットワーク接続からVmWareNetworkの仮想ネットワークを全て有効にする。
    - ipconfig -> `192.168.183.1` で認識されているはず。
    - ping 192.168.183.128 で接続を確認。
    - Matlabコンソールから`rosinit(192.168.183.128)` をする。
    - `rostopic list` を実行。つながっているはず。
