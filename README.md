# PetFinder
Kaggle competition "PetFinder", they need to calculate popularity of some pet's photos.
## Description
A picture is worth a thousand words. But did you know a picture can save a thousand lives? Millions of stray animals suffer on the streets or are euthanized in shelters every day around the world. You might expect pets with attractive photos to generate more interest and be adopted faster. But what makes a good picture? With the help of data science, you may be able to accurately determine a pet photo’s appeal and even suggest improvements to give these rescue animals a higher chance of loving homes.

PetFinder.my is Malaysia’s leading animal welfare platform, featuring over 180,000 animals with 54,000 happily adopted. PetFinder collaborates closely with animal lovers, media, corporations, and global organizations to improve animal welfare.

Currently, PetFinder.my uses a basic Cuteness Meter to rank pet photos. It analyzes picture composition and other factors compared to the performance of thousands of pet profiles. While this basic tool is helpful, it's still in an experimental stage and the algorithm could be improved.

In this competition, you’ll analyze raw images and metadata to predict the “Pawpularity” of pet photos. You'll train and test your model on PetFinder.my's thousands of pet profiles. Winning versions will offer accurate recommendations that will improve animal welfare.

If successful, your solution will be adapted into AI tools that will guide shelters and rescuers around the world to improve the appeal of their pet profiles, automatically enhancing photo quality and recommending composition improvements. As a result, stray dogs and cats can find their "furever" homes much faster. With a little assistance from the Kaggle community, many precious lives could be saved and more happy families created.

Top participants may be invited to collaborate on implementing their solutions and creatively improve global animal welfare with their AI skills.

## Data
In this competition, your task is to predict engagement with a pet's profile based on the photograph for that profile. You are also provided with hand-labelled metadata for each photo. The dataset for this competition therefore comprises both images and tabular data.

#### How Pawpularity Score Is Derived
The Pawpularity Score is derived from each pet profile's page view statistics at the listing pages, using an algorithm that normalizes the traffic data across different pages, platforms (web & mobile) and various metrics.
Duplicate clicks, crawler bot accesses and sponsored profiles are excluded from the analysis.
#### Purpose of Photo Metadata
We have included optional Photo Metadata, manually labeling each photo for key visual quality and composition parameters.
These labels are not used for deriving our Pawpularity score, but it may be beneficial for better understanding the content and co-relating them to a photo's attractiveness. Our end goal is to deploy AI solutions that can generate intelligent recommendations (i.e. show a closer frontal pet face, add accessories, increase subject focus, etc) and automatic enhancements (i.e. brightness, contrast) on the photos, so we are hoping to have predictions that are more easily interpretable.
You may use these labels as you see fit, and optionally build an intermediate / supplementary model to predict the labels from the photos. If your supplementary model is good, we may integrate it into our AI tools as well.
In our production system, new photos that are dynamically scored will not contain any photo labels. If the Pawpularity prediction model requires photo label scores, we will use an intermediary model to derive such parameters, before feeding them to the final model.
#### Training Data
train/ - Folder containing training set photos of the form {id}.jpg, where {id} is a unique Pet Profile ID.
train.csv - Metadata (described below) for each photo in the training set as well as the target, the photo's Pawpularity score. The Id column gives the photo's unique Pet Profile ID corresponding the photo's file name.
#### Example Test Data
In addition to the training data, we include some randomly generated example test data to help you author submission code. When your submitted notebook is scored, this example data will be replaced by the actual test data (including the sample submission).

test/ - Folder containing randomly generated images in a format similar to the training set photos. The actual test data comprises about 6800 pet photos similar to the training set photos.
test.csv - Randomly generated metadata similar to the training set metadata.
sample_submission.csv - A sample submission file in the correct format.
#### Photo Metadata
The train.csv and test.csv files contain metadata for photos in the training set and test set, respectively. Each pet photo is labeled with the value of 1 (Yes) or 0 (No) for each of the following features:

Focus - Pet stands out against uncluttered background, not too close / far.

Eyes - Both eyes are facing front or near-front, with at least 1 eye / pupil decently clear.

Face - Decently clear face, facing front or near-front.

Near - Single pet taking up significant portion of photo (roughly over 50% of photo width or height).

Action - Pet in the middle of an action (e.g., jumping).

Accessory - Accompanying physical or digital accessory / prop (i.e. toy, digital sticker), excluding collar and leash.

Group - More than 1 pet in the photo.

Collage - Digitally-retouched photo (i.e. with digital photo frame, combination of multiple photos).

Human - Human in the photo.

Occlusion - Specific undesirable objects blocking part of the pet (i.e. human, cage or fence). Note that not all blocking objects are considered occlusion.

Info - Custom-added text or labels (i.e. pet name, description).

Blur - Noticeably out of focus or noisy, especially for the pet’s eyes and face. For Blur entries, “Eyes” column is always set to 0.
