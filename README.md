Device configuration for the Samsung Tab Pro 8.4
Copyright (C) 2019 The LineageOS Project
Copyright (C) 2019 Valera Chigir <valera1978@tut.by>
Copyright (C) 2020 Gigabyte

 Licensed under the Apache License, Version 2.0 (the "License");
 you may not use this file except in compliance with the License.
 You may obtain a copy of the License at

      http://www.apache.org/licenses/LICENSE-2.0

------------------------------------------------------------------

* Description

  This repository is for ColtOS on Samsung Tab Pro 8.4 (mondrianwifi)

* How To Build ColtOS for Samsung Tab Pro 8.4

  - Make a workspace

mkdir ~/bin

cd ~/bin

  - Do repo init & sync

repo init -u git://github.com/Colt-Enigma/platform_manifest.git -b c10

  - Create .repo/local_manifests/roomservice.xml with the following content:

```
<?xml version="1.0" encoding="UTF-8"?>
<manifest>
  <project name="hyakki-/android_device_samsung_mondrianwifi" path="device/samsung/mondrianwifi" remote="github" />
  <project name="hyakki-/android_kernel_samsung_msm8974" path="kernel/samsung/msm8974_tab" remote="github" revision="lineage-17.1_pro" />
  <project name="hyakki-/android_vendor_samsung_mondrianwifi" path="vendor/samsung/mondrianwifi" remote="github" />
  <project name="LineageOS/android_device_samsung_qcom-common" path="device/samsung/qcom-common" remote="github" />
  <project name="LineageOS/android_hardware_samsung" path="hardware/samsung" remote="github" />
</manifest>
```

repo sync

. build/envsetup.sh
lunch colt_mondrianwifi-userdebug

make colt
