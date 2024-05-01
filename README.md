# Darknet-Detection

## Introduction
Organizations and individuals are at serious risk 
for  security  breaches  thanks  to  the  darknet,  which  gives 
cybercriminals a lot of leeway. This project acknowledges the 
urgency  of  addressing  these  security  issues  and  shielding 
against potential cyberattacks. One of the primary purposes of 
darknet detection is to identify and track the spread of malware, 
such as viruses and other malicious software. Using the darknet 
for  illegal  purposes  presents  a  big  challenge  for  law 
enforcement agencies. This project aims to help with legal 
investigations by creating efficient darknet traffic detection 
mechanisms, possibly leading to the identification and capture 
of cyber criminals. Through continuous surveillance of 
darknet traffic, organizations will be able to detect and mitigate 
malware infections in their initial stages, preventing potential 
attacks. Effective  darknet  traffic  detection  enables  security 
teams to proactively defend against emerging cyber threats by 
revealing  new  strategies  and  vulnerabilities  used  by  threat 
actors. This darknet monitoring for detecting signs of stolen 
or  leaked  data  leads  organizations  to  recognize  that  their 
sensitive information is being traded or exposed as an early 
warning, which enables them to prevent further data leaks. 
Considering the ever-evolving landscape of cyber threats and 
the ever-changing methods employed by attackers, the effective 
detection of darknet traffic can provide valuable insights for 
security  teams,  informing  them  about  new  tactics  and 
vulnerabilities used by threat actors. Moreover, this effort can 
help  organizations be  able  to  defend  against  cyberattacks 
proactively by monitoring and detecting suspicious patterns in 
darknet traffic.

## Dataset

The dataset is [CICDarknet2020](https://www.unb.ca/cic/datasets/darknet2020.html), which is 
an  amalgam  of  two  datasets, [ISCXTor2016](https://www.unb.ca/cic/datasets/tor.html) and 
[ISCXVPN2016](https://www.unb.ca/cic/datasets/vpn.html), to cover both Tor and VPN traffic. This 
dataset is a collaborative effort involving the Canadian Institute 
for  Cybersecurity  (CIC),  based on the  University  of  New 
Brunswick in Fredericton, and contributions from Arash Habibi 
Lashkari, Gurdip Kaur, and Abir Rahali [(DIDarknet: A Contemporary Approach to Detect and Characterize the Darknet Traffic using Deep Image Learning)](https://dl.acm.org/doi/10.1145/3442520.3442521).

this dataset encompasses 141,530 instances, each defined by 83 features as mentioned in Table 1, offering a unique perspective on the intricacies of the digital underworld.
Darknet, characterized as unused address space, operates passively accepting incoming packets while refraining from supporting outgoing ones. This passive nature raises skepticism about communications from this dark space, often associated with probing, backscatter, or misconfiguration. Darknets, also known as network telescopes, sinkholes, or blackholes, have limited legitimate hosts, making the analysis of their traffic pivotal for cybersecurity.
The dataset originates from groundbreaking research aiming to detect and characterize VPN and Tor applications, representative of darknet traffic. Characteristics encompass a spectrum of standard network flow metrics, including source and destination IP addresses, port numbers, communication protocols, flow duration, and packet counts and lengths. A crucial feature, 'Flow Bytes/s,' underwent preprocessing, with 47 missing values judiciously dropped due to their minimal impact relative to the dataset size.
Within the [CICDarknet2020 dataset](https://www.unb.ca/cic/datasets/darknet2020.html), a two-layered approach generates both benign and darknet traffic in Table 1, further categorized into distinct types associated with specific applications in Table 2. It can be observed in Fig. 1, dataset details outline the number of samples for benign and darknet traffic, providing insights into the complexity and diversity of the dataset.

*Table 1: Dataset Characteristics and Scenario 1 target labels*
| Attribute  | Descriction | 
| :---         |     :---:      |    
| Instances  | 141,530 |
| Features | 83 |
| Target Lables | Non-Tor, NonVPN, Tor, VPN |    

<br>   

*Table 2: Scenario2-Target Labels*
| Traffic Category  | Applications Used | 
| :---         |     :---:      |    
| Audio-Stream  | Vimeo and Youtube |
| Browsing | Firefox and Chrome |
| Chat | ICQ, AIM, Skype, Facebook and Hangouts |
| Email | SMTPS, POP3S and IMAPS |
| P2P | uTorrent and Transmission (BitTorrent) |
| Transfer | Skype, FTP over SSH (SFTP), FTP over SSL (FTPS) using Filezilla and an external service |
| Video-Stream | Vimeo and Youtube |
| VOIP | Facebook, Skype and Hangouts voice calls |

<br>

<img src="https://github.com/MahsaaPk/Darknet-Detection/assets/138306478/464284ad-9c46-4912-bcca-77f66f8859a3" width="400" height="300">
*Fig. 1. Visual Representation of the dataset*

## Methodology

In this project, a two-layered generation process is utilized that involves an ensemble of Random Forest + XGBoost, NN + Random Forest, and NN + XGBoost. This process is employed first to detect darknet and benign traffic and then to classify darknet traffic into categories such as Audio-Stream, Browsing, Chat, Email, P2P, Transfer, Video-Stream, and VOIP. This study extends an invitation to unravel the mysteries of the darknet, showcasing the significance of early threat detection and proactive defense in the realm of cybersecurity.

## Results and Discussion

### Performance evaluation metrics
The next stage is to assess the model's efficacy using some metrics after data preparation, applying these two models, and receiving the output. We used precision and recall, F1 score, and accuracy in evaluating our models.
Precision specifies that out of total positive predictions, what is the percentage of the actual accurate result. To calculate precision, we can use (1).
𝑃𝑟𝑒𝑐𝑖𝑠𝑖𝑜𝑛 = 𝑇𝑃/𝑇𝑃+𝐹𝑃 (1)
The rate of precisely anticipated positive observations divided by the total number of observations in the class is known as recall. We can use (3) to determine recall.
𝑅𝑒𝑐𝑎𝑙𝑙 = 𝑇𝑃/𝑇𝑃+𝐹𝑁 (2)
The F1-score is calculated as the weighted average of precision and recall. As a result, both false positive (FP) and false negative (FN) are considered in this score. The F1-score is frequently more helpful than the accuracy. This is defined as follows:
𝐹1 = 2×(𝑃𝑒𝑟𝑐𝑖𝑠𝑖𝑜𝑛×𝑅𝑒𝑐𝑎𝑙𝑙)/𝑃𝑒𝑟𝑐𝑖𝑠𝑖𝑜𝑛+𝑅𝑒𝑐𝑎𝑙𝑙 (3)
The percentage of accurately anticipated findings to all findings is called accuracy. It is the most basic and widely used performance metric. To calculate accuracy,
𝐴𝑐𝑐𝑢𝑟𝑎𝑐𝑦 = 𝑇𝑃+𝑇𝑁/𝑇𝑃+𝑇𝑁+𝐹𝑃+𝐹𝑁×100 (4)
Furthermore, for better evaluation of our results, we used k-fold cross-validation. We used 5-fold of our complete dataset in this instance. By reducing the problems related to a single train-test split, K-fold cross-validation aims to give a more solid and trustworthy estimate of a model's performance. In our context, K-fold cross-validation presents several significant benefits. First off, 5-fold cross-validation aids in reducing problems with our dataset randomness and variability. The evaluation results become less reliant on a particular random split when the training and evaluation process is repeated five times using different subsets. By doing this, it is possible to guarantee that the model's performance is representative and unaffected by a specific data partition. It offers a more thorough evaluation of our model's capacity for generalization. The model is exposed to different patterns in the data through various combinations of training and test sets. This makes it easier to determine whether the model generalizes well to different parts of the data or overfits to particular subsets. Additionally, 5-fold cross-validation finds a compromise between statistical robustness and computational efficiency. Higher numbers of folds provide more accurate estimates of model performance, but they also require more processing power. Five folds are frequently regarded as a good compromise because they provide a manageable balance between managing the computational cost and obtaining stable performance estimates.
### Discussion
In the binary classification we aimed at distinguishing between benign and darknet traffic, a set of initial models, including Random Forest, Decision Tree, K-Nearest Neighbors, Logistic Regression, and XGBoost, were thoroughly evaluated. Table 7 demonstrates these models’ performances. The Random Forest model exhibited exceptional performance with precision n, recall, and F1-score values of 0.997 each, demonstrating its accuracy and proficiency in differentiating between benign and darknet traffic instances. Similarly, the Decision Tree model showed commendable recall (0.996) and an F1-Score of 0.996, emphasizing its effectiveness. K-Nearest Neighbors demonstrated robust performance with a recall of 0.991 and an F1-Score of 0.991. Logistic Regression and XGBoost showcased strong precision (0.998), recall (0.998), and F1-Score (0.998) values, indicating their ability to accurately identify positive instances. These models are integral components of the comprehensive evaluation process. Beyond the baseline models, the analysis progressed to consider more intricate ensemble approaches, specifically NN + XGBoost and NN + Random Forest. The NN + XGBoost ensemble exhibited competitive performance, achieving a recall and F1-Score of 0.99. However, it did not surpass the perfection observed in some baseline models. In contrast, the NN + Random Forest ensemble emerged as a standout performer, achieving perfect precision, recall, and F1-Score values of 1.00. These flawless metrics signify an optimal balance and accuracy in distinguishing between benign and darknet traffic instances, positioning the ensemble as a robust and advanced solution. In comparison to the baseline models, the ensemble approaches, particularly the NN + Random Forest, elevated the overall performance to unprecedented levels.

*Table 7: Binary Classification Results*
| Model  | Precision | Recall | F1-Score
| :---         |     :---:      |    :---:      |    :---:      |   
| Random Forest  | 0.997 | 0.997 | 0.997 |
| Decision Tree | 0.997 | 0.996 | 0.996 |
| K-Nearest Neighbors | 0.991 | 0.991 | 0.991 |  
| Logistic Regression | 0.998 | 0.998 | 0.998 | 
| XGBoost | 0.998 | 0.998 | 0.998 |
| NN + XGBoost | 0.99 | 0.99 | 0.99 |
|  NN + Random Forest | 1.00 | 1.00 | 1.00 |


While for the multi-class classification, the ensemble models, NN + Random Forest and NN + XGBoost and Random Forest + XGBoost exhibited commendable performance with a consistent precision, recall, and F1-score of 0.89, 0.89 and 0.926 respectively. It is important to note that the results of NN + Random Forest and NN + XGBoost while good, did not surpass the baseline models. The baseline models, including Random Forest, Decision Tree and XGBoost achieved slightly higher performance with precision, recall, and F1-score values ranging from 0.915 to 0.926 as shown in Table 8. However, Random Forest + XGBoost outperforms all of the baseline models.
The ensemble models' performance, though not surpassing all the baselines, still reflects a solid and competitive outcome. These results suggest that the combination of Neural Networks with Random Forest or XGBoost contributed to effective classification but did not yield a significant improvement over the individual baseline models. While Random Forest + XGBoost had a great competition against the baseline models. Though, Further refinement and tuning may be explored to enhance the ensemble models' performance and potentially surpass all the baseline models in future iterations.

*Table 8: Multi-class Classification Results*
| Model  | Precision | Recall | F1-Score
| :---         |     :---:      |    :---:      |    :---:      |   
| Random Forest  | 0.926 | 0.923 | 0.923 |
| Decision Tree | 0.917 | 0.915 | 0.916 |
| XGBoost | 0.926 | 0.915 | 0.916 |
| NN + XGBoost | 0.89 | 0.89 | 0.89 |
|  NN + Random Forest | 0.89 | 0.89 | 0.89 |
|  Random Forest + XGBoost | 0.931 | 0.925 | 0.926 |

Figures 2 and 3 is the confusion matrix of NN + Random Forest and Random Forest + XGBoost models, showing the difference between the original truth value and the model's predicted value. The results shown in the confusion matrices affirm the overall effectiveness of the models in correctly classifying both binary and multi-class darknet traffic scenarios. The high counts of TP and low counts of FP and FN demonstrate the models' proficiency and reliability in distinguishing between different classes, reinforcing their practical utility in cybersecurity applications.

<img src="https://github.com/MahsaaPk/Darknet-Detection/assets/138306478/e37e809f-6a5e-442c-8105-d55694f91638" width="400" height="300">

*Fig. 2. Confusion Matrix of NN+Random Forest for binary classification*

<br>

<img src="https://github.com/MahsaaPk/Darknet-Detection/assets/138306478/1f3b7b72-cae6-48c3-8705-14b072b0bfc2" width="400" height="300">

*Fig. 3. Confusion Matrix of Random Forest+XGBoost for multi-class classification*

The results we obtained emphasize the importance of our study, in the field of detecting darknet traffic and enhancing cybersecurity. The binary classification results clearly show how effective our ensemble models, NN + Random Forest, are in distinguishing between darknet traffic. The precision, recall, and F1 score metrics provide an evaluation that confirms the model's high accuracy and strong performance.
Our study successfully accomplished its goal of improving cybersecurity through the development and validation of detection mechanisms. Analyzing the tradeoff between precision and recall in binary classification highlights the strengths of each model, which supports our assertion that the NN + Random Forest model outperforms others across evaluation metrics. An F1 score of 1.00 indicates a balanced combination of precision and recall, further reinforcing the reliability of this model in identifying darknet traffic. While our ensemble models demonstrate performance, it's important to acknowledge their limitations. The effectiveness of these models might depend on factors such as the quality and representativeness of the training dataset. Real world variations in darknet scenarios could present challenges that require updates and adaptations to address. Additionally, scalability in large scale network environments may be influenced by resources.
Nevertheless, it is worth noting some advantages. Combining neural networks with XGBoost or Random Forest is a powerful method that takes advantage of the strengths of each model, resulting in a comprehensive and reliable solution. The interplay between precision and recall provides insights, empowering cybersecurity professionals to make informed choices.
Our research adds to the body of knowledge by proving the effectiveness of ensemble models and illuminating the subtleties of their performance in the categorization of binary and multi-class darknet data. The trials show how crucial dynamic hyperparameter adjustment is, as well as how model choice affects overall performance. The importance of ongoing dataset enrichment and the necessity of adaptation in the face of changing cyberthreats are emphasized in the experiments' lessons learned. Enhancing the models' practical utility are real-time integration and response capabilities. To find domain-specific features for increased model accuracy, the study emphasizes the value of working with cybersecurity professionals.

