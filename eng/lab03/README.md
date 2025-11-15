
# 🧩 Exercise 3: MetaOSINT – What does a photo reveal?

EXIT (Exchangeable Image File Format) is a standard for storing metadata in image, audio, and other multimedia files. Devices such as digital cameras and mobile phones often store this information in photos.

This exercise is designed to explore the information that can be revealed using **metadata in photos (EXIF)**. Using various tools, we will analyze photos and determine the information that can be revealed using MetOSINT, such as the location and time of the photo, the device, and other hidden data.

## 1️⃣ Introduction: Gathering information about photos

The objectives of the exercise are:  
✅ Understand the importance of metadata in digital photos.  
✅ Use OSINT tools to analyze EXIF ​​data.  
✅ Assess the risks associated with sharing images online.  
✅ Develop critical thinking about privacy and digital footprints.  

---

### MetaOSINT

MetaOSINT is a technique within OSINT (Open Source INTelligence), where we analyze the metadata of files, especially photos, in order to obtain information about the origin, device, author or time of creation.

If a photo contains metadata, we can obtain, for example, GPS data from it and determine the exact location of the photo. Metadata also reveals whether the image has been edited later. We can also obtain information about the author and device from the metadata.

---

### 🔍 Tools for analyzing EXIF ​​metadata

There are many tools for analyzing metadata.

The most commonly used tool is exiftool (https://exiftool.org/)

[Documentation and GitHub](https://github.com/exiftool/exiftool)

There are also many online tools:
- [https://www.pic2map.com/](https://www.pic2map.com/)
- [https://exif.tools/](https://exif.tools/)
- [Online Exif Viewer](https://onlineexifviewer.com/)

---

## 🖼️ Using MetaOSINT on photos

We will use a test image with EXIF ​​data included, we will take the photo from the exif-samples collection, but you can also use your own photo, e.g. from a mobile phone

First, let's select a photo:
- [https://github.com/ianare/exif-samples](https://github.com/ianare/exif-samples)
- Or a photo with your own mobile phone (make sure it has the location included).

---

## 📝 Instructions

1. **Select a photo with EXIF ​​data**
- It is preferable that this is a photo that was taken with a mobile device with location enabled.

2. **Upload the photo to the online tool**
- Open [https://pic2map.com](https://pic2map.com) or [https://exif.tools](https://exif.tools)
- Upload your test image.
- View the analysis results: GPS, date, time, device, orientation, etc.

3. **Analyze the location**
- If the coordinates are shown, paste them into Google Maps or OpenStreetMap and check the actual location.
- Compare whether the location matches reality.

4. **Analyze the time and device**
- When was the photo taken?
- With which device?
- Are there other interesting data (e.g. orientation, software, etc.)?

---

## 📝 Analysis and Report

Answer the following questions:

1. What was the exact location (coordinates and address)?

The coordinates are 38° 55' 34.35" N, 94° 37' 21.40" W, and the address is Tomahawk Creek Trail, Leawood, Johnson County, Kansas, 66211, United States.

3. When was the image taken?

The image was taken on 2021-04-24 at 14:52:29 (GMT -05:00). 
   
5. What other metadata did you notice?

   There are camera information, file information, date and time, GPS information, and location information.

7. What surprised you?

I was surprised by how much information you can find in just one picture.

9. What would you recommend to someone who regularly posts images online?

I would recommend disabling the GPS function when taking pictures and checking the metadata before posting images online.
    

---

## 💬 Reflection

- Should everyone remove EXIF ​​data before posting an image?

It depends on who is posting the image and for what purpose. For example, if you want to prove that a picture was taken in a specific place, such as a park, then it is okay to keep the EXIF data, including GPS coordinates. However, for private or personal photos it is recommended to remove this information before posting them publicly.
  
- How can we protect ourselves from the misuse of such information?

The best protection is not to publish personal pictures or other sensitive information online, or to share them only with trusted people. We can also protect ourselves by removing EXIF data before posting, disabling GPS on our devices, using strong privacy settings on social media.

- Have you ever posted an image that contained such metadata? What would your reaction be today?

I am convinced that I still have some old pictures online that contain such metadata, because back then I didn’t know much about personal cybersecurity. Today I am much more careful about what kind of data I upload or share online.

---

## 🛠️ Additional

- Try using the `exiftool` tool locally in the terminal:
```bash
exiftool image.jpg
```

---

## 📌 Important

The purpose of this exercise is not to violate the privacy of others, but to **make you aware of how quickly and easily it is to reveal data from an image** and consequently **learn how to use digital content safely**.

---

## 🧼 How to remove EXIF ​​metadata

If we want to remove all metadata from an image before publishing it, we have several options:

### 🖥️ Using `exiftool` (command line)

1. Install the tool:
```bash
sudo apt install libimage-exiftool-perl # Debian/Ubuntu
brew install exiftool # macOS
```

2. To remove all metadata from an image (create a copy):
```bash
exiftool -all= image.jpg
```

3. To overwrite an existing file:
```bash
exiftool -all= -overwrite_original image.jpg
```

---

### 🌐 Online tools (for test cases)

- [https://www.verexif.com/en/](https://www.verexif.com/en/)
- [https://www.exifremove.com/](https://www.exifremove.com/)

⚠️ Warning: Do not use online tools for sensitive images.

---

### 🪟 Windows

- Right click on the image → **Properties** → **Details**
- Click **Remove Properties and Personal Information**

---

### 📱 Mobile phones

**Android**:
- Photo Exif Editor
- Scrambled Exif (F-Droid)

**iOS**:
- Metapho
- Exif Metadata

## References

1. Pic2Map, *Photo location viewer*, https://www.pic2map.com/
2. Exif.tools, *Online EXIF data viewer*. https://exif.tools/
3. Online Exif Viewer, *View EXIF data online*. https://onlineexifviewer.com/
4. Verexif, *Remove EXIF metadata online*. https://www.verexif.com/en/
5. Exif Remove, *Remove EXIF metadata from photos*. https://www.exifremove.com/
6. OpenAI. (2025), *ChatGPT* (Aug 2025) [Large language model], https://chat.openai.com/
