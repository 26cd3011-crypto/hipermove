# Third-party notices

HiperMove is an original hack-day implementation. It loads these third-party
components at runtime; their code and model files are not vendored here.

## MediaPipe Tasks Vision and BlazePose GHUM

Google AI Edge MediaPipe Tasks Vision 1.1.1 JavaScript package and the Pose Landmarker
Lite model are loaded from official CDN/model-hosting locations. MediaPipe source
and the BlazePose GHUM model card identify Apache License 2.0.

- Project: https://github.com/google-ai-edge/mediapipe
- Pose Landmarker docs: https://developers.google.com/edge/mediapipe/solutions/vision/pose_landmarker
- BlazePose GHUM model card: https://storage.googleapis.com/mediapipe-assets/Model%20Card%20BlazePose%20GHUM%203D.pdf
- License: https://www.apache.org/licenses/LICENSE-2.0

## Gemma 4

The optional session summary uses Google's hosted Gemini API with the
gemma-4-26b-a4b-it model. Gemma 4 model weights are provided under Apache 2.0.
This app sends only user-approved summary metrics, never the video or pose
frames. Gemini API use is subject to Google's current API terms and policies.

- Gemma 4 model card: https://ai.google.dev/gemma/docs/core/model_card_4
- Gemini API guide: https://ai.google.dev/gemma/docs/core/gemma_on_gemini_api
- Google AI terms: https://ai.google.dev/gemini-api/terms

## Fonts and icons

The interface uses system fonts, CSS shapes and inline SVG. No external font
or icon package is included.
