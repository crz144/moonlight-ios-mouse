# Intro

This is a simple fork to implement some minor fixes for keyboard + mouse support on Moonlight for TvOS 

The core mouse fix was brought up by bartleman [here:](https://github.com/moonlight-stream/moonlight-ios/pull/676)

This is a private API fix, meaning it would not pass Apple app store review (hence why it is not implemented in the core repo).
A more comprehensive fix would be for Apple to properly forward mouse input events, at which point app store versions would work properly. 
You can boost the odds of this by duplicating bartleman's original feedback (ID: FB24369577) at feedback.apple.com

# Deployment

Multiple methods, but the simplest:

- Pre-requisite: The compiled .ipa file will clash with existing Moonlight installations. Delete the existing app on your AppleTV to proceed.
1. Grab the .ipa file from the artifacts of the most recent run in the "Actions" tab.
2. Install [Sideloadly](https://sideloadly.io/). Sideloading from Windows is only supported if you have an AppleTV with a USB port, and it must be connected directly to the Windows Machine. If you have an AppleTV model with no USB port, you will need a MacOS computer to proceed.
3. On your Apple TV, navigate to Settings > Remotes and Devices > Remote App and Devices. Leave the Apple TV open to this screen.
4. Open Sideloadly, and check that your Apple TV appears in the "iDevice" dropdown.
5. Enter the email address associated with your Apple ID, click the large "IPA" icon to the left, and select the .ipa file downloaded earlier.
6. Click "Start" and Sideloadly will begin installing the compiled app to your Apple TV. You will be prompted for a pin from the Apple TV as well as your ICloud account password throughout this process.

Note that if you don't have a paid Apple Developer account, you will need to follow steps 4-6 once a week, as sideloaded apps are only available for 7 days on the Apple developer free tier.


# Moonlight iOS/tvOS

[![CI](https://github.com/moonlight-stream/moonlight-ios/actions/workflows/ci.yml/badge.svg)](https://github.com/moonlight-stream/moonlight-ios/actions/workflows/ci.yml)

[Moonlight for iOS/tvOS](https://moonlight-stream.org) is an open source client for [Sunshine](https://github.com/LizardByte/Sunshine) and NVIDIA GameStream. Moonlight for iOS/tvOS allows you to stream your full collection of games and apps from your powerful desktop computer to your iOS device or Apple TV.

Moonlight also has a [PC client](https://github.com/moonlight-stream/moonlight-qt) and [Android client](https://github.com/moonlight-stream/moonlight-android).

Check out [the Moonlight wiki](https://github.com/moonlight-stream/moonlight-docs/wiki) for more detailed project information, setup guide, or troubleshooting steps.

[![Moonlight for iOS and tvOS](https://moonlight-stream.org/images/App_Store_Badge_135x40.svg)](https://apps.apple.com/us/app/moonlight-game-streaming/id1000551566)

## Building
* Install Xcode from the [App Store page](https://apps.apple.com/us/app/xcode/id497799835)
* Run `git clone --recursive https://github.com/moonlight-stream/moonlight-ios.git`
  *  If you've already clone the repo without `--recursive`, run `git submodule update --init --recursive`
* Open Moonlight.xcodeproj in Xcode
* To run on a real device, you will need to locally modify the signing options:
    * Click on "Moonlight" at the top of the left sidebar
    * Click on the "Signing & Capabilities" tab
    * Under "Targets", select "Moonlight" (for iOS/iPadOS) or "Moonlight TV" (for tvOS)
    * In the "Team" dropdown, select your name. If your name doesn't appear, you may need to sign into Xcode with your Apple account.
    * Change the "Bundle Identifier" to something different. You can add your name or some random letters to make it unique.
    * Now you can select your Apple device in the top bar as a target and click the Play button to run.
