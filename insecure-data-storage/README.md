# Insecure Data Storage

## Overview

Insecure data storage occurs when sensitive information is stored locally on a mobile device without adequate protection such as encryption, secure storage mechanisms, or proper access controls.

Mobile applications may store sensitive data in locations such as Shared Preferences, SQLite databases, local files, logs, or cached data.

## Objective

The objective of this lab is to assess whether sensitive application data is stored securely on the Android device.

## Testing Methodology

The application was assessed using static and dynamic analysis techniques.

### Static Analysis

- Decompiled the APK using JADX
- Reviewed AndroidManifest.xml
- Inspected application source code
- Reviewed references to Shared Preferences, SQLite, and local file storage

### Dynamic Analysis

- Installed the application in a controlled lab environment
- Interacted with application functionality
- Examined local storage locations using adb
- Checked whether sensitive data persisted after logout or app closure

## Findings

Sensitive information was found stored locally without adequate protection.

Examples of sensitive information that may be exposed include:

- User identifiers
- Session-related values
- Application configuration data
- Credentials or tokens
- Personal information

## Risk Impact

If an attacker gains access to the device or application storage, insecurely stored data may lead to:

- Information disclosure
- Session hijacking
- Account compromise
- Privacy violations
- Increased impact from device theft or malware

## Remediation

Recommended remediation steps include:

- Avoid storing sensitive information locally unless required
- Encrypt sensitive data before storing it
- Use Android Keystore for cryptographic key management
- Clear sensitive data after logout
- Disable sensitive data exposure through logs or cache
- Apply secure session management practices

## Tools Used

- MobSF
- JADX
- adb
- Android Studio

## References

- OWASP Mobile Top 10
- OWASP MASVS
- CWE-922: Insecure Storage of Sensitive Information
