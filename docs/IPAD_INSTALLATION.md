# Installing LLMFarm on iPad

This guide provides instructions for installing LLMFarm on your iPad.

## Option 1: Install from App Store (Recommended)

The easiest way to install LLMFarm on your iPad is through the official App Store:

1. Open the **App Store** on your iPad
2. Search for **"LLM Farm"**
3. Tap **Get** or the cloud download icon
4. Once installed, open the app from your home screen

**App Store Link:** https://apps.apple.com/app/llm-farm/id6461209867

> **Note:** This App Store link is taken from the project README. Verify the link works for your region.

## Option 2: Install via TestFlight (Latest Beta Version)

To get the latest features and updates before they're released to the App Store:

1. Install **TestFlight** from the App Store if you don't have it already
2. Open this link on your iPad: https://testflight.apple.com/join/6SpPLIVM
3. Tap **Accept** to join the beta
4. Tap **Install** to download LLM Farm
5. Once installed, you can open it from your home screen

> **Note:** TestFlight invitation links may have limited slots or expiration dates. If the link doesn't work, check the project README or GitHub for an updated link.

**Note:** Beta versions may contain experimental features and bugs.

## Option 3: Build and Install from Source (Advanced)

For developers who want to build from source:

### Prerequisites

- A Mac computer with Xcode installed (Xcode 14.2 or later)
- An Apple Developer account (free account works for development)
- Your iPad connected to your Mac via USB

### Steps

1. **Clone the repository with submodules:**
   ```bash
   git clone --recurse-submodules https://github.com/guinmoon/LLMFarm
   cd LLMFarm
   ```

2. **Open the project in Xcode:**
   ```bash
   open LLMFarm.xcodeproj
   ```

3. **Configure signing:**
   - Select the **LLMFarm** project in the Project Navigator
   - Select the **LLMFarm** target
   - Go to **Signing & Capabilities** tab
   - Under **Team**, select your Apple Developer account
   - Xcode will automatically create a provisioning profile

4. **Select your iPad as the destination:**
   - Connect your iPad to your Mac via USB
   - Trust the computer on your iPad if prompted
   - In Xcode's toolbar, click the device selector (next to the scheme selector)
   - Choose your iPad from the list

5. **Build and run:**
   - Click the **Run** button (▶️) in Xcode, or press `Cmd + R`
   - Xcode will build the app and install it on your iPad
   - If prompted on your iPad, go to **Settings → General → VPN & Device Management** and trust your developer certificate

6. **Keep the app on your device:**
   - The app will remain on your iPad as long as your provisioning profile is valid (7 days for free accounts, 1 year for paid)
   - You can re-run from Xcode to refresh the provisioning

### Building for Distribution (Requires Paid Developer Account)

If you have a paid Apple Developer account, you can create an IPA for distribution:

1. **Archive the app:**
   ```bash
   xcodebuild archive \
     -project LLMFarm.xcodeproj \
     -scheme LLMFarm \
     -sdk iphoneos \
     -configuration Release \
     -archivePath ./build/LLMFarm.xcarchive
   ```

2. **Export IPA:**
   ```bash
   xcodebuild -exportArchive \
     -archivePath ./build/LLMFarm.xcarchive \
     -exportPath ./build/ipa \
     -exportOptionsPlist ExportOptions.plist
   ```

3. **Install IPA on iPad:**
   - Use Apple Configurator 2, Xcode, or other IPA installation tools
   - Or upload to TestFlight for easier distribution

## Option 4: Sideload with AltStore (No Developer Account Required)

For users without an Apple Developer account:

1. **Install AltStore:**
   - Download AltStore from https://altstore.io/
   - Follow the installation instructions for your computer (Mac or Windows)
   - Install AltStore on your iPad

2. **Get the IPA:**
   - Download the pre-built IPA from the GitHub Actions artifacts (if available)
   - Or build it yourself using Xcode

3. **Sideload with AltStore:**
   - Open AltStore on your iPad
   - Tap the **+** button
   - Browse and select the LLMFarm IPA file
   - AltStore will install the app

4. **Refresh the app:**
   - Apps sideloaded with AltStore need to be refreshed every 7 days
   - Keep AltStore installed and connected to your Mac/PC periodically to refresh

## iPad-Specific Features

LLMFarm is optimized for iPad with the following features:

- **Full iPad support:** Works on all iPad models running iOS 16.4 or later
- **Landscape and Portrait modes:** Rotate your iPad for your preferred view
- **Split View and Slide Over:** Use LLMFarm alongside other apps
- **Large screen optimization:** Takes advantage of iPad's larger display

## Troubleshooting

### "Untrusted Developer" Error
If you see this error after installation:
1. Go to **Settings → General → VPN & Device Management**
2. Find your developer certificate
3. Tap **Trust**

### App Keeps Crashing
- Make sure you're running iOS 16.4 or later
- Try restarting your iPad
- Reinstall the app

### Free Account Provisioning Expired
- Apps installed with a free Apple Developer account expire after 7 days
- Re-run the app from Xcode to refresh the provisioning

### Need Help?
- Check the [Wiki](https://github.com/guinmoon/LLMFarm/wiki)
- Join the [Telegram chat](https://t.me/llmfarm_chat)
- Open an issue on [GitHub](https://github.com/guinmoon/LLMFarm/issues)

## System Requirements

- **Operating System:** iOS/iPadOS 16.4 or later
- **Devices:** All iPad models that support iOS 16.4+
- **Storage:** At least 2GB free space (models require additional storage)
- **RAM:** Recommended 4GB or more for better performance

## Getting Started

After installation, you can:

1. Download pre-configured models from the app
2. Import your own GGUF models
3. Start chatting with AI models directly on your iPad
4. Use advanced features like RAG (Retrieval Augmented Generation)
5. Create custom model configurations

For more information, visit:
- Official website: https://llmfarm.tech
- Documentation: https://llmfarm.tech/docs (if available)
- GitHub Wiki: https://github.com/guinmoon/LLMFarm/wiki
