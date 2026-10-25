# HiperMove privacy and data handling

**Version:** 25 October 2026  
**Audience:** adults aged 18 or older

HiperMove is a hack-day prototype, not a production health service. The event operator or deployment owner should add a named privacy contact and review this notice for the laws and event rules that apply before public deployment.

## Data flow

- After the user presses **Start camera** and grants permission in the browser, the app reads the live camera stream for pose estimation. It requests no microphone access and does not record, upload, or store camera frames, audio, or raw pose landmarks. The camera remains active until the user chooses **Turn camera off**, revokes browser permission, or closes the page.
- MediaPipe Pose Landmarker performs frame inference on the device. Google states that MediaPipe APIs may separately send usage and performance metrics to Google, including inference counts, hardware-level performance, app identifiers, general media characteristics, and system environment details. The app asks for consent before loading MediaPipe.
- If an operator enables the adult-only Gemma API and the user presses the recap button, the browser sends the server only the repetition count, rounded average bottom angle, sampled-frame count, and live tracking duration. The server may send these numbers to the Gemini API. It does not send video, audio, frame images, filenames, raw landmarks, or free-text user input. A standalone HTML copy calculates its recap in the browser and sends no session metrics to the app server.
- The app does not create accounts or retain sessions. The summary endpoint enforces a global 60-request-per-hour in-memory limit without keeping client IP addresses. A deployment provider and Google may process ordinary connection and service metadata under their own terms.
- The adult age and telemetry-consent checkbox is not saved; it resets when the page is reloaded. Camera access is requested separately by the browser only after the user presses **Start camera**.

## Adult audience and Gemini terms

The Gemini API terms require API users to be at least 18 and restrict API clients directed to, or likely to be accessed by, people under 18. HiperMove's Gemini endpoint remains disabled unless the operator provides both GEMINI_API_KEY and GEMINI_API_18_PLUS_ONLY=true. Do not set this flag for a mixed-age or under-18 audience. The client checkbox is a self-attestation and does not replace audience controls or compliance review.

Before enabling Gemma, the operator must accept and follow Google's current API terms using their own account. Unpaid and paid Gemini API services have different data-use terms. Do not submit sensitive, confidential, or personal information to an unpaid service. Review Google's terms and log policy before use.

## Use limitations

Outputs are camera-based estimates and may be wrong. The app does not judge technique, safety, fitness, or health and must not be used for medical, rehabilitation, or clinical decisions. Users should start the camera only for people who consent to being processed and should obtain permission from anyone visible in frame.

## Reference policies

- MediaPipe terms: https://developers.google.com/edge/mediapipe/legal/tos
- Gemini API terms: https://ai.google.dev/gemini-api/terms
- Gemini API logging: https://ai.google.dev/gemini-api/docs/logs-policy