# LabelImgTreeSpecies
Instructions on how to install and use LabelImg for Windows/Linux and macOS

# LabelImg
THe first step towards using object detection is installing and training a model using LabelImg. LabelImg is a graphical annotation tool that is written in Python. The outputs are saved as XML files in either PASAL VOC format (default) or in YOLO format. 

## Prerequisites 
To run LabelImg there are various ways to install the program on your computer, below are detailed instructions for Windows, macOS and Linux Systems

1. Ubuntu Linux

Depending on your python version the installation steps will differ

1.1 Python 2 + Qt4

sudo apt-get install pyqt4-dev-tools
sudo pip install lxml
make qt4py2
python labelImg.py
python labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]

1.2 Python 3 + Qt5 (Recommended)

sudo apt-get install pyqt5-dev-tools
sudo pip3 install -r requirements/requirements-linux-python3.txt
make qt5py3
python3 labelImg.py
python3 labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]

2. macOS

Again this is dependent on your python version and it is reccommended that you install LabelImg within a virtualenvironment. 

2.1 Python 2 + Qt4

brew install qt qt4
brew install libxml2
make qt4py2
python labelImg.py
python labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]

2.2 Python 3 + Qt5 (Recommended)

brew install qt  # Install qt-5.x.x by Homebrew
brew install libxml2

or using pip

pip3 install pyqt5 lxml # Install qt and lxml by pip

make qt5py3
python3 labelImg.py
python3 labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]


2.3 Python 3 Virtualenv (Recommended)

Virtualenv can avoid a lot of the QT / Python version issues

brew install python3
pip3 install pipenv
pipenv run pip install pyqt5==5.13.2 lxml
pipenv run make qt5py3
python3 labelImg.py
[Optional] rm -rf build dist; python setup.py py2app -A;mv "dist/labelImg.app" /Applications

3. Windows
Using command line one can install LabelImg

3.1 Install Python, PyQt5 and install lxml.

Open cmd and go to the labelImg directory

pyrcc4 -o line/resources.py resources.qrc
For pyqt5, pyrcc5 -o libs/resources.py resources.qrc

python labelImg.py
python labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]

3.2 Windows Binary installation

The simplest way to install LabelImg for Windows is to download the installer and directly install as a program
The link to the binary is below. 

https://tzutalin.github.io/labelImg/

Following this link will take you to a download site with the various versions of labelImg. The latest version is suggested for download. 
Follow the installation steps and open the GUI of LabelImg. 


## How to use LabelImg
1. Open the version of LabelImg you installed or run it using python.
2. Once GUI is open, change the save directory to one of your choice. This will save the xml files to that folder which will make finding them later easier. 
3. Make sure that the images you want to label are saved in JPEG format. Open file and choose the image. 
4. Once open, begin labelling individual objects within the image by using Create/nRectBox button, this will allow you to create bouding boxes that are rectangular in shape around the objects you want to detect. 
5. After left-clicking and dragging to create a bounding box, label the object what you would like or use a pre-defined library. We labelled with the latin name of the tree species. 
6. Create as many labels as you would like to train your model, it is suggested that 80% are used to train and 20% are used to test your model. 
7. Save your xml output by clicking the save button or click the File-> Save as... and save the xml to a location of your choice. 
8. Once completed, you can train it with more images that are annotated or close the LabelImg GUI and then move towards exporting the xml.

