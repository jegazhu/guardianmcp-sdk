# GuardianMCP SDK

Behavioral Identity Verification SDK for Android.

GuardianMCP analyzes behavioral biometrics (touch dynamics, session patterns, device usage) to detect anomalous behavior indicating account takeover, bots, or stolen devices.

## Features

- Behavioral biometrics authentication
- On-device AI (LSTM Autoencoder)
- No biometric storage
- Privacy-first architecture
- Offline inference (<10 ms latency)

## Architecture

Sensor Layer → Feature Engine → LSTM Autoencoder → Risk Engine → SDK API

## SDK Usage

```kotlin
GuardianMCP.initialize(context)

val risk = GuardianMCP.evaluateSession()

if(risk > 80){
    requireBiometricAuth()
}
