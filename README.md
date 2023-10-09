# Getting started
```
Step 1: copy project to root file and run with android studio. Check flutter and dart version.
```

```
Step 2: copy all runner app icon , info.plist, firebase google service to anode folder

```

```
Step 3: delete iOS folder

```

Step 4 : flutter create --platform ios . To create iOS folder
Step 5 : flutter clean ,flutter pub get in terminal
Step 6 : now replace info.plist, app icons, google service firebase back to iOS folder - (if you did not change iOS previously then this can be skipped)
Step 7: add the google service file by Xcode in runner folder
Step 8 : check iOS deployment target make it 13 and uncomment it
Step 9 : put these code in below of pod file post_install do |installer|
  installer.generated_projects.each do |project|
        project.targets.each do |target|
            target.build_configurations.each do |config|
                config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '13.0'
             end
        end
 end
    installer.pods_project.targets.each do |target|
    flutter_additional_ios_build_settings(target)
  end
end

Step 10: if you use stripe Apple Pay then remove pkDidSelectShippingMethodSignature from applepaycontext.swift from let pk didselectshippingmethod

		Name:Aidlink Assistant
 key : CW735Y264Y

		Name:Aidlink Recruiter
		Key ID:YT3FGM84H5
		Services:Apple Push Notifications service (APNs)


Error when upload to App Store Connect : upload complete from Xcode but not appearing in App Store .

I also ended up having similar problems on different components of my app. Ended up adding all these keys so far (after updating to Xcode8/iOS10):
<key>NSPhotoLibraryUsageDescription</key>
<string>This app requires access to the photo library.</string>
<key>NSMicrophoneUsageDescription</key>
<string>This app does not require access to the microphone.</string>
<key>NSCameraUsageDescription</key>
<string>This app requires access to the camera.</string>
Checkout this developer.apple.com link for full list of property list key references.
gem cleanup
brew uninstall cocoapods
sudo gem uninstall cocoapods
sudo gem install cocoapods -v 1.10.0 -n /usr/local/bin   ***`add cocoapod version u want to install`***
sudo gem install cocoapods-user-defined-build-types
pod install --repo-update



in Xcode, go to FIRFirestoreSettings.mm file, look for(go to pods, and you will see FIRbaseFirestore folder, open it);-
ABSL_CONST_INIT extern "C" const int64_t kFIRFirestoreCacheSizeUnlimited =
    Settings::CacheSizeUnlimited;

and change it to;-
extern "C" const int64_t kFIRFirestoreCacheSizeUnlimited =
Settings::CacheSizeUnlimited;

run your build, this should work



This steps worked for me after failing many times.
STEP 1: Navigate to the location of the folder containing Pods-resources.sh
STEP 2: Open the terminal type cd and then drag the folder containing Pods-resources.sh to terminal and hit enter.
STEP 3: the run this command>> chmod a+x Pods-resources.sh
STEP 4: restart xcode and open your xxx.xworkspace
STEP 5: enjoy
