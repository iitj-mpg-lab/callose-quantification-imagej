# callose-quantification-imagej
Automated ImageJ-based workflow for callose quantification using machine learning segmentation and particle analysis.
The scripts and trained model provided in this repository are associated with the protocol described in the article *“An optimized protocol to detect callose deposition in soybean lateral roots during fungal infections.”*
## 🔍 Use case
- Measures root area from microscopy images  
- Identifies callose deposits using a trained Weka classifier  
- Automatically counts callose particles  
 
## 📁 Repository structure
- `macros/` – ImageJ macro scripts (`.ijm`)  
- `model/` – Pre-trained classifier for callose detection  
- `example_data/` – Sample images and outputs  

## ▶️ Quick start
1. Open your image in ImageJ and set the scale  
2. Run `Clear Measure Resize.ijm` to crop and measure root area  
3. Load and apply the classifier (`Callose quantification.model`)  
4. Run `Callose analyse particles.ijm` to count callose deposits

# Callose Quantification Protocol (sample output)


### Step 1: Setting the Scale of the Image
![Step 1: Setting the scale](https://github.com/iitj-mpg-lab/callose-quantification-imagej/blob/main/example_data/image1.png?raw=true)

[cite_start]Steps for setting the scale of the image: [cite: 32]
* [cite_start]**A.** Open the images saved in .tiff format in ImageJ software and using the line tool draw a line over the scale (the yellow line represents the line drawn over the scale). [cite: 32]
* [cite_start]**B.** On the menu bar, select "Analyse" >> "Set Scale" and then make changes accordingly highlighted in red and proceed to "OK". [cite: 32]

---

### Step 2: Crop and Measure Root Tissue
![Step 2: Crop and measure](https://github.com/iitj-mpg-lab/callose-quantification-imagej/blob/main/example_data/image2.png?raw=true)

[cite_start]Steps to crop and measure the root tissue in the image: [cite: 111]
* [cite_start]**A.** Using a polygon tool, mark a boundary around the root tissue. [cite: 112]
* [cite_start]**B.** On the menu bar, select "Plugins" >> "Macros" >> "Run". [cite: 113]
* [cite_start]**C.** Select the "Clear Measure Resize.ijm" to run the macro. [cite: 114]
* [cite_start]**D.** The resulting image after processing along with the area of the cropped root tissue will appear. [cite: 115]
* [cite_start]**E & F.** Save the image in .tiff format in "Cropped images" folder. [cite: 116]

---

### Step 3: Segmentation of the Cropped Images
![Step 3: Segmentation](https://github.com/iitj-mpg-lab/callose-quantification-imagej/blob/main/example_data/image3.png?raw=true)

[cite_start]Steps for segmentation of the cropped images: [cite: 198]
* [cite_start]**A.** Open the cropped image for segmentation and select "Plugins" >> "Segmentation" >> "Trainable Weka Segmentation". [cite: 198]
* [cite_start]**B.** A Trainable Weka Segmentation dialog box will appear; select "Load classifier". [cite: 199]
* **C.** Select "Callose segmentation.model" file. [cite_start]A dialog box will appear indicating successful loading of the classifier. [cite: 200]
* [cite_start]**D.** Select "Apply classifier" option. [cite: 200]
* **E.** Select the file to be segmented i.e., the images that were cropped. [cite_start]A dialog box of probability maps will appear; select "No" option. [cite: 200]
* [cite_start]**F.** The resulting image is segmented and save this image in .tiff format in "Segmented images" folder. [cite: 200]

---

### Step 4: Enumerate Callose Depositions
![Step 4: Enumerate callose](https://github.com/iitj-mpg-lab/callose-quantification-imagej/blob/main/example_data/image4.png?raw=true)

[cite_start]Steps to enumerate the callose depositions: [cite: 253]
* [cite_start]**A.** Open Segmented images in ImageJ software. [cite: 253]
* [cite_start]**B.** On the menu bar, select "Plugins" >> "Macros" >> "Run". [cite: 254]
* [cite_start]**C.** Select "Callose analyse particles" option. [cite: 254]
* [cite_start]**D.** The resulting image shows the number of callose depositions detected by the tools. [cite: 255]
* [cite_start]**Summary:** A summary dialog box will appear showing the number of callose depositions in the image analysed (i.e., counts). [cite: 256]



### Please refer the article titled "An optimized protocol to detect callose deposition in soybean lateral roots during fungal infections" for detailed step by step usage instructions. 


