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

Table 1: Dataset Characteristics and Scenario 1 target labels
| Attribute  | Descriction | 
| :---         |     :---:      |    
| Instances  | 141,530 |
| Features | 83 |
| Target Lables | Non-Tor, NonVPN, Tor, VPN |
