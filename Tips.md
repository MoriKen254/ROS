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

## Learning ROS for Robotics Programming
### `catkin_make`した時、`opencv2/nonfree/features2d.hpp no such file or directory.`と怒られる。
```
sudo add-apt-repository --yes ppa:xqms/opencv-nonfree
sudo apt-get update
sudo apt-get install libopencv-nonfree-dev
```

##Matlab on Windows
###kubuntu のturtlebotと繋ぐ
- kubuntu
  - `gazebo TrutleBot World` を開く。コンソールに色々出てきてgazeboが立ち上がる。
  - `Publicized address: 192.168.183.128` がgazeboっぽい。
  - というか、デスクトップの左上にでかーく書いてあった…。
- Windowsマシン
  - とりあえずつなげる
    - ネットワーク接続からVmWareNetworkの仮想ネットワークを全て有効にする。
    - ipconfig -> `192.168.183.1` で認識されているはず。
    - ping 192.168.183.128 で接続を確認。
    - Matlabコンソールから`rosinit(192.168.183.128)` をする。
    - `rostopic list` を実行。つながっているはず。
    - 適当にsubscribeは出来るはず。多分publishできない。
  - Fire Wallの設定
      - Fire Wall を解放しないとpublishだけできないっぽい。
      - VMと接続中のネットワーク(デフォはパブリックだった)のTCPを解放する。UDPは切っても切らなくても挙動は変わらない。
      - 運が良ければpublish時にWindowsが勝手にダイアログを出してくれるので、そのまま許可する。
