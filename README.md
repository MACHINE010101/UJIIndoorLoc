# UJIIndoorLoc

The UJIIndoorLoc Data Set is a collection of WiFi signals data collected from access points placed in different indoor locations, such as offices, classrooms, and corridors. The data has been preprocessed to extract a set of features related to signal strength, position, and orientation, and it includes measurements of signal strengths from 520 access points. The goal of the dataset is to predict the indoor location of a person based on the received WiFi signals. The dataset has 19,937 instances and 529 features, making it a useful resource for indoor localization and navigation tasks, including classification, clustering, and regression.

source: https://archive.ics.uci.edu/ml/datasets/UJIIndoorLoc

In the machine learning repository, this dataset provides relevant papers for further study. As my first initiative, I'm going to look at a conference paper titled "UJIIndoorLoc: A new multi-building and multi-ﬂoor database for WLAN ﬁngerprint-based indoor localization problems"

Atribute Information:

    Attribute 001 (WAP001): Intensity value for WAP001. Negative integer values from -104 to 0 and +100. Positive value 100 used if WAP001 was not detected. (dBm)
    Attribute 520 (WAP520): Intensity value for WAP520. Negative integer values from -104 to 0 and +100. Positive Vvalue 100 used if WAP520 was not detected. (dBm)
    Attribute 521 (Longitude): Longitude. Negative real values from -7695.9387549299299000 to -7299.786516730871000
    Attribute 522 (Latitude): Latitude. Positive real values from 4864745.7450159714 to 4865017.3646842018.
    Attribute 523 (Floor): Altitude in floors inside the building. Integer values from 0 to 4.
    Attribute 524 (BuildingID): ID to identify the building. Measures were taken in three different buildings. Categorical integer values from 0 to 2.
    Attribute 525 (SpaceID): Internal ID number to identify the Space (office, corridor, classroom) where the capture was taken. Categorical integer values.
    Attribute 526 (RelativePosition): Relative position with respect to the Space (1 - Inside, 2 - Outside in Front of the door). Categorical integer values.
    Attribute 527 (UserID): User identifier (see below). Categorical integer values.
    Attribute 528 (PhoneID): Android device identifier (see below). Categorical integer values.
    Attribute 529 (Timestamp): UNIX Time when the capture was taken. Integer value.

## Relevant Papers
IUJIIndoorLoc: A new multi-building and multi-floor database for WLAN fingerprint-based indoor localization problems

One of common thing that many application wants to make use of is automatic user localization. This works by using an electronic device, usually a mobile phone to compute the user latitude, longitude and altitude. Many problems occur in indoor settings, we cannot make use of GPS sensor to locate a user because GPS signal gets lost in indoor environments.

Many people have tried to make use of WLANs, which is especially a good approach because it doesn't require any extra equipment and can be found on most smartphones plus WLANs are now ubiquitous. WLAN Fingerprint-based positioning systems are based on the Received Signal Strength Indicator (RSSI) value, a radio map of the area where the users should be detected is constructed and later the user obtains the signal strength of all visible access points of the WLAN.

One important draw-back in this field is the lack of a common database for comparison purposes, the UJIIndoorLoc database is presented to overcome this gap.

UJIIndoorLoc database contains characteristics such as:

    Covers a surface of 108703m 2 including 3 buildings with 4 or 5 floors
    The number of different places is 933
    21049 sampled points have been captured: 19938 for training/learning and 1111 for validation/testing
    Validation (or testing) samples were taken 4 months after Training ones.
    The number of different wireless access points (WAPs) appearing in the database is 520
    Data were collected by more than 20 users using 25 different models of mobile devices

This work is based on an infrastructure-less approache, mainly taking advantage of the powerful mobile phone sensors.
UJIIndoorLoc DATABASE DESCRIPTION

The whole database contains 21049 records, each record is directly related to 529 numeric elements:

    001-520 RSSI levels (dBm)
    521-523 Real world coordinates of the sample points
    524 BuildingID
    525 SpaceID
    526 Relative position with respect to SpaceID
    527 UserID
    528 PhoneID
    529 Timestamp

A total number of 520 WAPs appear in the database and the 520-element vector from each record contains the raw intensity levels of the detected WAPs from a single WiFiscan. One scan cannot capture the adresses of every WAP possible, the unrelated WAP will be filled with an artificial RSSI value of +100dBm. The paper also mention that the main factors that affects the number of WAPs reported by WIFi scan are location and the phone model.

## What is my goal?

I want to create a machine learning model that can accurately predict the location of devices inside buildings using WLAN fingerprinting. The objective is to estimate the building, floor and coordinates (latitude and longitude).

## Research Questions

What is the best machine learning algorithm for indoor localization predictions?

Which phones are used by which users?

What are Graph Neural Networks and how graph operate?
