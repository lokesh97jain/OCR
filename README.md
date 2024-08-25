# OCR

OCR ([*Optical Character Recognition*](https://en.wikipedia.org/wiki/Optical_character_recognition)) with Google's AI technology ([Cloud Vision API](https://cloud.google.com/vision/docs/ocr)).

The Vision API can detect and extract text from images.

## Install

1. Download [Python 3.6+](https://www.python.org/downloads/) or follow [this guide from Google Cloud](https://cloud.google.com/python/setup).
2. Clone or [download]([https://github.com/lokesh97jain/OCR]) this repository.
3. Install the required dependencies by running the following command in your terminal:
   
   ```sh
   !pip install google-cloud-vision google-auth.
   ```

## Usage

```
usage: OCR [-h] [--url] [--document] [--languages LANGUAGES] [--full] [--confidence CONFIDENCE] [--key KEY] path

positional arguments:
  path                  path to image

optional arguments:
  -h, --help            show this help message and exit
  --url                 specify the path for an external image located on the Web (http:// or https://) or in Google Cloud Storage (gs://)
  --document            optimized for dense images
  --languages LANGUAGES, --language LANGUAGES
                        specify language hints from https://cloud.google.com/vision/docs/languages (comma separated)
  --full, --verbose     show full description (paragraphs, per-word confidence, boundaries...)
  --confidence CONFIDENCE
                        display possible mistakes for symbols with low confidence. Default: 0.6
  --key KEY             explicitly define the path to your service account JSON credentials
```

## Authentication

Follow [these instructions](https://cloud.google.com/vision/docs/detect-labels-image-client-libraries#before-you-begin) to set up a project with the Cloud Vision API enabled:

1. [Select or create a Google Cloud Platform project](https://console.cloud.google.com/projectselector2). Project name suggestion: *OCR*
2. [Enable Cloud Vision API for your project](https://console.cloud.google.com/apis/library/vision.googleapis.com).
3. [Create a service account and get your JSON credentials](https://console.cloud.google.com/iam-admin/serviceaccounts/create). Service account name suggestion: *OCR*
4. [Make sure that billing is enabled for your project](https://console.cloud.google.com/billing/linkedaccount).
   
   Pricing is based on [Google Cloud Vision API quota](https://cloud.google.com/vision/pricing#prices): *1,000 requests/month free*

To authenticate your project you need to reference the service account JSON credentials you just downloaded.
You have different options to do it, choose what you prefer:


### service_account.json file

The JSON you downloaded in step 3 place it inside this repository folder.

### `--key` parameter

Another option is to explicitly specify the `--key` parameter on every script execution:

`OCR image.jpg --key "/path/to/service_account.json"`


### Environment variable

You can also [set the ***GOOGLE_APPLICATION_CREDENTIALS*** environmental variable](https://cloud.google.com/docs/authentication/provide-credentials-adc#local-key):

<details>
  <summary><a><i>bash</i></a></summary>

  <p>Add to your <code>.bash_profile</code> file:</p>
  
  <code>export GOOGLE_APPLICATION_CREDENTIALS="/path/to/service_account.json"</code>

</details>

<details>
  <summary><a><i>fish</i></a></summary>

  <p>Add to your <code>config.fish</code> file:</p>
  
  <code>set -gx GOOGLE_APPLICATION_CREDENTIALS "/path/to/service_account.json"</code>

</details>


## Example
![TAJ](https://github.com/user-attachments/assets/2b8763f5-1546-4e80-a7fc-8ce61452ad55)

from File: TAJ.jpg

Result: [output.txt](https://github.com/user-attachments/files/16738473/output.txt)





