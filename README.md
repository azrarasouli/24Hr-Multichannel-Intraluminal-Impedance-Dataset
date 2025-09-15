# Dataset Description: MII Dataset for Gastroesophageal Reflux Disease (GERD)
## Overview 
Gastroesophageal reflux disease (GERD) is a prevalent digestive disorder that affects millions globally. Traditional diagnostic techniques, such as endoscopy and 24-hour pH monitoring, are often used to evaluate patients with GERD symptoms. However, many patients with normal endoscopy and pH measurements continue to experience symptoms and do not respond adequately to anti-secretory therapy.
Multichannel Intraluminal Impedance-pH (MII-pH) monitoring is an innovative technique that detects intraluminal bolus movement and identifies gastroesophageal refluxes (GER) without the use of radiation. First introduced by Silny et al. in 1991, MII-pH monitoring is now considered the gold standard for diagnosing GERD. This method not only assesses bolus transit but also determines the physical state of the bolus. Despite its clinical significance, there is limited biomedical research analyzing MII-pH data, highlighting a need for further software development in this area.

## Data Acquisition  
For this dataset, 24-hour MII-pH monitoring was conducted on patients with normal endoscopy who did not respond to anti-secretory therapy. Data were archived at Noor and Hazrat-e-Ali Asghar Hospital in Isfahan, Iran. Each monitoring session lasted approximately 24 hours, utilizing a mobile recording device (Ohmega Impedance Ambulatory pH Meter; MMS, Enschede, Netherlands). 
The six-channel impedance-pH catheter was passed transnasally under topical anesthesia and positioned 5 cm above the lower esophageal sphincter (LES) to record pH at 5 cm and impedance at 3, 5, 7, 9, 15, and 17 cm proximal to the LES. Data from both the impedance channels and pH electrodes were stored on portable data recorders (Ohmega R; MMS B.V., Enschede, Netherlands) and processed using MMS database software for raw data format conversion. MII-pH data were collected at a sampling frequency of 50 Hz, then downloaded onto a computer.
We selected archived data from 26 patients of varying ages and sexes for this study. The MII signals allow for the identification of all types of GER, independent of pH measurements. To simplify the analysis and avoid multi-modal processing, the pH data were excluded, resulting in a dataset focused solely on unit impedance.
To ensure informative and balanced data, we selected at least four episodes for each 24-hour MII-pH signal, focusing on periods proximate to GER events. Each MII episode spans two minutes and contains swallows and at least one GER event. Characterizing GERs from MII data is crucial for diagnosing GERD. A total of 202 episodes were reviewed with the assistance of three experienced gastroenterologists to specify the characteristics of each GER event. A binary mask indicates GER events across all six channels.

## Data Structure
This dataset was originally used in the IAI_2023 challenge, with the corresponding paper available at [paper link]. For the IAI_2023 challenge, the dataset was divided into training, testing, and hidden subsets, released sequentially: the training dataset first, followed by the testing dataset, and finally the hidden dataset during the live competition for validation. The dataset comprises 202 episodes, including 208 GER events, from 26 patients. Training and testing sets were sourced from distinct individuals, while the hidden set was randomly sampled from any patient. Episodes in the training and testing folders contain 6,001 rows, while hidden folder episodes contain 6,000 rows.
For our new paper, the dataset remains identical to the IAI_2023 challenge dataset. However, the division differs: we randomly split the entire dataset and applied a hold-out method, reserving 20 MII episodes for testing and using the remaining 182 episodes for training and validation.

| Folders	| Files	| # rows	| # columns |	type	| # Episodes |	# Subjects |	# GERs|
|Train	MII_Train.csv|	882147	|6	|float	|147|	18|	148|
|FLAG_GER_Train.csv|	882147|	6|	binary|			
|Test	MII_Test.csv|	162027|	6	|Float|	27	|8	|27|
|FLAG_GER_Test.csv|	162027|	6|	binary|			
|Hidden	MII_Hidden.csv|	168000|	6|	float	|28	|-	|33|
	FLAG_GER_Hidden.csv	168000	6	binary			

