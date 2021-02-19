gphoto-dslr-role
=========

Ansible role to install gPhoto so that you can use a DSLR as a webcam.

This role was derived from [Ben Chapman's blog post](https://medium.com/nerdery/dslr-webcam-setup-for-linux-9b6d1b79ae22)

This was also designed as part of a desktop provisioning playbooks found here <https://github.com/billwheatley/provision-desktop>

Requirements
------------

- A distribution with `dnf` or `apt`

Role Variables
--------------

none

Example Playbook
----------------

```yaml
- name: My Playbook
  hosts: all
  roles:
    - role: gphoto-dslr-role
```

Using gPhoto Examples
---------------------

With your camera plugged into the USB port and switched on:

```console
# Take a picture and download to current dir
gphoto2 --capture-image-and-download

# Find your correct video device
v4l2-ctl --list-devices |grep v4l2loopback -A 1

#Stream Video
gphoto2 --stdout --capture-movie | ffmpeg -i - -vcodec rawvideo -pix_fmt yuv420p -threads 0 -f v4l2 /dev/video4

#Stream Video with GPU acceleration
gphoto2 --stdout --capture-movie | ffmpeg -hwaccel nvdec -c:v mjpeg_cuvid -i - -vcodec rawvideo -pix_fmt yuv420p -threads 0 -f v4l2 /dev/video4

```

License
-------

GPLv2

Author Information
------------------

Contact via [Github](https://github.com/billwheatley/)
