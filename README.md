step 1: install dependencies,

 sudo apt install build-essential cmake git pkg-config libgtk- 
   3-dev \libavcodec-dev libavformat-dev libswscale-dev 
   libv4l-dev \libxvidcore-dev libx264-dev libjpeg-dev 
   libpng-dev libtiff-dev \gfortran openexr libatlas-base- 
   dev python3-dev python3-numpy \libtbb2 libtbb-dev 
   libdc1394-22-dev
Step 2: create a directory opencv_build and Clone the necessary repositories as shown below,

mkdir ~/opencv_build && cd ~/opencv_build
git clone https://github.com/opencv/opencv.git
git clone https://github.com/opencv/opencv_contrib.git
step 3: cd into opencv directory, inside create another directory called build and cd into it,

cd ~/opencv_build/opencv
mkdir build && cd build
step 4: evoke Cmake to build OpenCV,

cmake -D CMAKE_BUILD_TYPE=RELEASE \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D INSTALL_C_EXAMPLES=ON \
-D INSTALL_PYTHON_EXAMPLES=ON \
-D OPENCV_GENERATE_PKGCONFIG=ON \ 
-D OPENCV_EXTRA_MODULES_PATH=~/opencv_build/opencv_contrib/modules \
-D BUILD_EXAMPLES=ON ..

make -j6 
step 6: install OpenCV, We use,

sudo make install
then check the version Of OpenCV to verify the installation:

pkg-config --modversion opencv4

for videos:

./bin/FaceLandmarkVid -f "../samples/changeLighting.wmv" -f "../samples/2015-10-15-15-14.avi"

for images:

./bin/FaceLandmarkImg -fdir "../samples/" -wild

for multiple faces in videos:

./bin/FaceLandmarkVidMulti -f ../samples/multi_face.avi

for feature extraction (facial landmarks, head pose, AUs, gaze and HOG and similarity aligned faces):

./bin/FeatureExtraction -verbose -f "../samples/default.wmv"



PASTE

/bin/FaceLandmarkVid -f "../samples/changeLighting.wmv" -f "../samples/2015-10-15-15-14.avi"
