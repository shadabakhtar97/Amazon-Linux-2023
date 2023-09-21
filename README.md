# Amazon-Linux-2023
Learn about Amazon Linux 2023 in Deep Dive

### How to change git git version 2.40.1 to old version in  amazon linux

To change the Git version on Amazon Linux to an older version, you can follow these steps:

1. **Check the Current Git Version**: Before downgrading Git, it's a good idea to check the current version to ensure that you're targeting the right version for the downgrade. You can do this by running:

   git --version

   Make a note of the current Git version.

2. **Remove the Current Git Version**: You'll need to remove the currently installed Git version. Use the `yum` package manager to do this:

   sudo yum remove git

3. **Find an Older Git Version**: To install an older Git version, you need to find the package corresponding to the desired version. You can do this by searching the available Git packages:

   yum list git --showduplicates

   This will display a list of available Git versions. Note the version you want to install, typically specified as `git.x86_64`, where `x` represents the major version number, and `64` indicates the architecture.

4. **Install the Older Git Version**: Install the desired older version of Git using `yum`. Replace `x` and `64` with the version you want:

   sudo yum install git-x.y.z

   Replace `x.y.z` with the specific version you want to install.

5. **Verify the Installed Git Version**: After the installation is complete, verify that the older Git version is now installed:

   git --version

6. **Optional: Pin the Git Version**: To prevent the system from automatically upgrading Git to a newer version in the future, you can lock the Git package to the currently installed version. This way, it won't get updated when you run system updates:

   sudo yum install yum-versionlock
   sudo yum versionlock add git-x.y.z

   Replace `x.y.z` with the specific version you installed.

Now you have successfully downgraded Git to the older version on your Amazon Linux system. Please note that specific package versions available may vary depending on your Amazon Linux distribution and the repositories you have configured. Be sure to choose an older Git version that is compatible with your system and requirements.
