# Unified Podfile for Fattmerchant iOS SDK Samples
workspace 'Fattmerchant-iOS-SDK-Samples.xcworkspace'

# Common configuration
platform :ios, '13.0'
use_frameworks!

# Fattmerchant SDK pod specification
def fattmerchant_sdk
  pod 'Fattmerchant', :path => '../Fattmerchant-iOS-SDK'
end

# Storyboard Sample Target
target 'Fattmerchant-iOS-SDK-Sample' do
  project 'Storyboard/Fattmerchant-iOS-SDK-Sample.xcodeproj'
  fattmerchant_sdk
end

# Swift UI Sample Target  
target 'Sample App (Swift UI)' do
  project 'Swift UI/Sample App (Swift UI).xcodeproj'
  fattmerchant_sdk
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['ENABLE_BITCODE'] = 'NO'
      config.build_settings['EXCLUDED_ARCHS[sdk=iphonesimulator*]'] = 'x86_64'
    end
  end
end
