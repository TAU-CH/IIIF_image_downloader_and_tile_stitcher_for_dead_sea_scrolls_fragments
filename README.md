This repository has been developed with the help of **[Bronson Brown deVost](https://github.com/Bronson-Brown-deVost)** and his project **[iiif_image_load](https://github.com/Bronson-Brown-deVost/iiif_image_load)**. 

# Download IIIF Image as Tiles and Stitch the Tiles

This notebook provides a script that enables you to download full images from an IIIF server. Using an image identifier, the script queries the server and downloads the individual tiles which are then stitched together to form the full image. This is because an IIIF server does not allow downloading images greater than 1000 x 1000 pixels. 

The IIIF image server defines an Image API and a Presentation API. The Image API specifies information that is needed to return an image in response to a standard HTTP request. The URL can specify the region, size, rotation, quality characteristics, and format of the requested image. The info.json file structure defines technical properties of the image such as the image size, tile size, image format, and color quality. 

The Presentation API provides information for online viewing of the images. The manifest.json file structure contains descriptive, rights, and linking information for the object and provides information that the client needs to begin to display something quickly to the user.

## Following the Dead Sea Scrolls (DSS) Fragment Images to Their Source

The Israel Antiquities Authority (IAA) photographs the Dead Sea Scroll fragment images and hosts them via an IIIF server (https://iaa.iiifhosting.com). The public image archive can be viewed here (https://www.deadseascrolls.org.il/explore-the-archive). The fragment manifests are available at https://dss.digitalbibleonline.org/manifests/all/. Each manuscript consists of several fragments, and each fragment is imaged from recto and verso using different wavelengths in infrared and color formats, which can be viewed at https://www.qumran-digital.org/qd-images/.

To download the fragment images for a given manuscript, first, we fetch the fragment manifest from https://dss.digitalbibleonline.org/manifests/all/. Then, we identify the identifier of the interested image format (i.e. recto and infrared) from the fragment manifest, and finally, we download the fragment image using the identifier from https://iaa.iiifhosting.com.

## Project Details

In this project, we provide a list of manuscript names and their identifiers (https://www.dropbox.com/s/2n2ozr9xrqd68kk/letter_detection_dataset_manuscripts.xlsx?dl=0). These manuscripts are dated internally and can be used as ground truth for manuscript dating problems. We have also shared the interested fragment image identifiers (https://github.com/beratkurar/hebrew_letter_detection/blob/main/fragment_identifiers.csv) that we gathered from the manifests (https://dss.digitalbibleonline.org/manifests/all/).
