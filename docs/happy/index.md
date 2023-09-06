Applications, Python libraries and Docker images for hyper-spectral data processing and modelling.

* [ADAMS](adams.md)
* [happy-tools](happy_tools/index.md)
* [Segment Anything](sam.md)
* [Segment Anything in High Quality](sam-hq.md)


# Notes on WSL2

The tools are all working under the Windows Subsystem for Linux. But Docker 
and graphical applications only work as long as you are using version 2 of 
WSL and your [Windows 10 is at least build 19044 (no restrictions with 
Windows 11)](https://learn.microsoft.com/en-us/windows/wsl/tutorials/gui-apps).

Here is how to switch WSL to version 2 as default by running the following
command:

```
wsl --set-default-version 2
```

You can view all your current images and what WSL version they are using
with the following command:

```
wsl --list -v
```

If you want to switch an existing image (e.g., `Ubuntu-22.04`) to version 2,
then you can run the following command:

```
wsl --set-version Ubuntu-22.04 2
```

Source: [https://stackoverflow.com/a/73164601](https://stackoverflow.com/a/73164601)
