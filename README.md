# ANPR-AWS

![AWS](https://github.com/user-attachments/assets/75976310-1416-4dcf-a6ae-cbe542b1c25c)

## Visualization

1. Go to **Kinesis Video Streams** and create a video stream.  
2. Go to **EC2** and launch a `t2.small` instance.  
3. SSH into the EC2 instance.  
4. Execute the following commands in the EC2 instance:  

### **Setup Commands**
```bash
sudo apt update

git clone https://github.com/awslabs/amazon-kinesis-video-streams-producer-sdk-cpp.git

mkdir -p amazon-kinesis-video-streams-producer-sdk-cpp/build

cd amazon-kinesis-video-streams-producer-sdk-cpp/build

sudo apt-get install libssl-dev libcurl4-openssl-dev liblog4cplus-dev libgstreamer1.0-dev \
libgstreamer-plugins-base1.0-dev gstreamer1.0-plugins-base-apps gstreamer1.0-plugins-bad \
gstreamer1.0-plugins-good gstreamer1.0-plugins-ugly gstreamer1.0-tools

sudo apt install cmake

sudo apt-get install g++

sudo apt-get install build-essential

cmake .. -DBUILD_DEPENDENCIES=OFF -DBUILD_GSTREAMER_PLUGIN=ON

make

sudo make install

cd ..

export GST_PLUGIN_PATH=`pwd`/build

export LD_LIBRARY_PATH=`pwd`/open-source/local/lib

### **Download Vidio**


