# XCTPore
//Public database containing images and mask pair of X-ray CT slices//


The dataset is stored in a Google Cloud Bucket and can be downloaded with the instructions from Annex A. The Bucket contains files like MA001_train, MA001_mask, MA002_train, MA002_mask …. TC002_train, TC002_mask. Each file is a .npy file and can be loaded with the np.save function. 
Each .npy file has either a “_train” or “_mask” suffix and the class it belongs to is written as it’s prefix. Files with “_train” suffix contains the training images in a (300, h, w) uint16 NumPy array. The bit-depth of each pixel is 16-bits (uint16). 
Files with “_mask” contains the mask for the training image in a (300, h, w) uint8 NumPy array. The mask at index i represents the mask for ith training image in the training data. The mask is segmented in the following format:
0 – Foreground
1 – Material
2 – Pore
For Example, a file named “MA001_train” means it is the training image for class MA001. The corresponding mask can be found in the file named “MA001_mask”



**Download Instructions**
1.	Go to Google Cloud Platform page: https://cloud.google.com/ . Click “Get started for free”
![alt text](https://github.com/BismaMutiargo/XCTPore/blob/main/Images/Step%201.png)

2. Follow the instructions on the screen until all three steps are completed.
![alt text](https://github.com/BismaMutiargo/XCTPore/blob/main/Images/Step%202.png)

3.	Install Google Cloud SDK by clicking “Google Cloud CLI Installer” in blue from the following page: https://cloud.google.com/sdk/docs/install
![alt text](https://github.com/BismaMutiargo/XCTPore/blob/main/Images/Step%203.png)

4.	After the .exe installer has finished downloading, execute the .exe installer and follow the instructions on the screen to complete the installation. 
![alt text](https://github.com/BismaMutiargo/XCTPore/blob/main/Images/Step%204.png)

5.	After the installation of the CLI is complete. Launch the CLI. A window similar to a command prompt window should appear. 
![alt text](https://github.com/BismaMutiargo/XCTPore/blob/main/Images/Step%205.png)



6.	Run the command “gcloud init”. When prompted for a numeric choice, input “1”. A network diagnostic should proceed automatically.
![alt text](https://github.com/BismaMutiargo/XCTPore/blob/main/Images/Step%206.png)

7. After the network diagnostic has completed successfully, input “Y” to login. A new window of your default internet browser should pop up, prompting a google login (similar to logging in to gmail).  
![alt text](https://github.com/BismaMutiargo/XCTPore/blob/main/Images/Step%207.png)

8.	After logging in at the pop-up browser, switch windows back to the cloud CLI. When prompted to pick a project, select the first project by inputting “1”. Take note that the project name will be different from the image below. Save the project name in its entirety somewhere safe.
![alt text](https://github.com/BismaMutiargo/XCTPore/blob/main/Images/Step%208.png)

9. The CLI is now setup
![alt text](https://github.com/BismaMutiargo/XCTPore/blob/main/Images/Step%209.png)



10.	The dataset is roughly 6GB in size. To download the dataset, replace the parts in purple and run the command to download the entire dataset:
```
gsutil -u PROJECT-NAME cp -r gs://datatest_13/XCTPore SAVE_DIRECTORY
```
```diff -
Warning: ```The command above will charge about USD$0.50 to your GCP account if it is executed without error. Any downloads will incur charges to your GCP account. It is to do the following before proceeding:
•	Ensure a stable internet connection
•	Download the entire dataset and keep a backup of the original dataset on your local machine to minimize charges. 
11.	To contribute to dataset, run the following command:
```
gsutil -u PROJECT-NAME cp -r DATASET_DIRECTORY gs://datatest_13/upload_xctpore
```

