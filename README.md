# Barcode_raspi_camera
This repository tells you how to scan any barcode either by uploading an image or by running raspberry pi camera capturing video
Installing ZBar (with Python bindings) for barcode decoding
The instructions to install ZBar in today’s post are largely based on his instructions, but with a few updates, the largest one being related to how we install the Python zbar  bindings themselves, ensuring we can:

    Use Python 3 (the official zbar  Python bindings only support Python 2.7)
    Detect and localize exactly where in the image the barcode is.

Installing the necessary software is an easy 3-step process.

Step 1: Install zbar  from the apt  or brew  repository

Installing ZBar for Ubuntu or Raspbian

Installing ZBar for Ubuntu can be accomplished with the following command:
An OpenCV barcode and QR code scanner with ZBar
Shell
$ sudo apt-get install libzbar0
1
	
$ sudo apt-get install libzbar0

Installing ZBar for macOS

Installing ZBar for macOS using brew is equally as easy (assuming you have Homebrew installed):
An OpenCV barcode and QR code scanner with ZBar
Shell
$ brew install zbar
1
	
$ brew install zbar

Step 2 (Optional): Create a virtual environment and install OpenCV

You have two options here:

    Use an existing virtual environment that has OpenCV ready to go (skip this step and head to Step 3).
    Or create a new, isolated virtual environment which involves installing OpenCV.

Virtual environments are a best practice for Python development and I highly encourage you to make use of them.

I elected to create a new, isolated Python 3 virtual environment and followed the Ubuntu (or macOS, depending on which machine I was using) OpenCV installation instructions linked on this page. The only change I made while following those instructions was to name my environment barcode :
An OpenCV barcode and QR code scanner with ZBar
Shell
$ mkvirtualenv barcode -p python3
1
	
$ mkvirtualenv barcode -p python3

Note: If you already have OpenCV installed on your system you can skip the OpenCV compile process and simply sym-link your cv2.so  bindings into the site-packages  directory of your new Python virtual environment.

Step 3: Install pyzbar

Now that I have a Python 3 virtual environment named barcode  on my machine, I activated the barcode  environment (yours might have a different name) and installed pyzbar :
An OpenCV barcode and QR code scanner with ZBar
Shell
$ workon barcode
$ pip install pyzbar
1
2
	
$ workon barcode
$ pip install pyzbar

If you are not using a Python virtual environment you can just do:
An OpenCV barcode and QR code scanner with ZBar
Python
$ pip install pyzbar
1
	
$ pip install pyzbar

If you’re trying to install pyzbar  into the system version of Python make sure you use the sudo  command as well.

now

open terminal 

open the directory where the code is saved

type 

$ python3 barcode_scanner_image.py --image <path_of_barcode_or_qr_code>

