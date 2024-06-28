# Enhancing Network Attack Classification through Ensemble Learning Techniques
In this project, I have used the Kaggle UNB CIC IOT 2023 Dataset to classify network attacks using ensemble learning techniques. The dataset contains 169 CSV files, each with 47 columns, and the output columns contain 34 different classes. Initially, I performed multiclass classification on these 34 classes. Subsequently, I grouped them into 8 classes and applied multiclass classification again. Finally, I consolidated these into 2 classes for binary classification. For each classification task, I used models such as Decision Tree, Random Forest, and XGBOOST, followed by applying ensemble learning techniques.

Author: Vivek Pal , Anamika Rajput                                 
Collaborators: Dr. Umang Garg, Assistant Professor, Amity University Madhya Pradesh      
# Table of Contents
Title and Description    
Acknowledgements    
Demo   
Deployment Documentation Environment Variables FAQ Features Feedback Github Profile - About Me Github Profile - Introduction Github Profile - Links Github Profile - Other Github Profile - Skills Installation Lessons License Logo Optimizations Related Roadmap Run Locally Screenshots Support Tech Running Tests Usage/Examples Used By

# Title and Description
This project aims to enhance network attack classification through the application of ensemble learning techniques on the UNB CIC IOT 2023 Dataset.       https://www.kaggle.com/datasets/madhavmalhotra/unb-cic-iot-dataset         
## Acknowledgements     
I would like to thank my professors, particularly Dr. Umang Garg, Assistant Professor at Amity University Madhya Pradesh, for their guidance and support throughout this project.      
## Authors      
- [Vivek Pal](https://github.com/Vivek7987)     
- [Umang Garg](https://scholar.google.co.in/citations?user=sLv_RAMAAAAJ&hl=en)
- [Anamika Rajput]()
## Demo 
- Information of a chunk of the data:

  <div id="df-91be0d00-0646-4c57-9cb7-344338a5fe43" class="colab-df-container">
    <div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>flow_duration</th>
      <th>Header_Length</th>
      <th>Protocol Type</th>
      <th>Duration</th>
      <th>Rate</th>
      <th>Srate</th>
      <th>Drate</th>
      <th>fin_flag_number</th>
      <th>syn_flag_number</th>
      <th>rst_flag_number</th>
      <th>psh_flag_number</th>
      <th>ack_flag_number</th>
      <th>ece_flag_number</th>
      <th>cwr_flag_number</th>
      <th>ack_count</th>
      <th>syn_count</th>
      <th>fin_count</th>
      <th>urg_count</th>
      <th>rst_count</th>
      <th>HTTP</th>
      <th>HTTPS</th>
      <th>DNS</th>
      <th>Telnet</th>
      <th>SMTP</th>
      <th>SSH</th>
      <th>IRC</th>
      <th>TCP</th>
      <th>UDP</th>
      <th>DHCP</th>
      <th>ARP</th>
      <th>ICMP</th>
      <th>IPv</th>
      <th>LLC</th>
      <th>Tot sum</th>
      <th>Min</th>
      <th>Max</th>
      <th>AVG</th>
      <th>Std</th>
      <th>Tot size</th>
      <th>IAT</th>
      <th>Number</th>
      <th>Magnitue</th>
      <th>Radius</th>
      <th>Covariance</th>
      <th>Variance</th>
      <th>Weight</th>
      <th>label</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>101692</th>
      <td>0.000000</td>
      <td>53.46</td>
      <td>5.94</td>
      <td>63.36</td>
      <td>32.282695</td>
      <td>32.282695</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.00</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.00</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>568.20</td>
      <td>54.06</td>
      <td>55.20</td>
      <td>54.215864</td>
      <td>0.357419</td>
      <td>54.06</td>
      <td>8.307598e+07</td>
      <td>9.5</td>
      <td>10.412846</td>
      <td>0.505921</td>
      <td>0.721418</td>
      <td>0.19</td>
      <td>141.55</td>
      <td>DDoS-TCP_Flood</td>
    </tr>
    <tr>
      <th>204963</th>
      <td>0.007573</td>
      <td>10275.00</td>
      <td>17.00</td>
      <td>64.00</td>
      <td>28143.121492</td>
      <td>28143.121492</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.00</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.00</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>525.00</td>
      <td>50.00</td>
      <td>50.00</td>
      <td>50.000000</td>
      <td>0.000000</td>
      <td>50.00</td>
      <td>8.301601e+07</td>
      <td>9.5</td>
      <td>10.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.00</td>
      <td>141.55</td>
      <td>DoS-UDP_Flood</td>
    </tr>
    <tr>
      <th>221721</th>
      <td>0.098575</td>
      <td>13.68</td>
      <td>1.22</td>
      <td>63.01</td>
      <td>3.350618</td>
      <td>3.350618</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.05</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.03</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>9143.02</td>
      <td>267.42</td>
      <td>1490.96</td>
      <td>869.630176</td>
      <td>562.563128</td>
      <td>873.56</td>
      <td>8.325337e+07</td>
      <td>9.5</td>
      <td>41.511237</td>
      <td>795.405003</td>
      <td>333780.832837</td>
      <td>0.95</td>
      <td>141.55</td>
      <td>DDoS-ICMP_Fragmentation</td>
    </tr>
    <tr>
      <th>22729</th>
      <td>0.000000</td>
      <td>0.00</td>
      <td>1.00</td>
      <td>64.00</td>
      <td>24.105126</td>
      <td>24.105126</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.00</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.00</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>441.00</td>
      <td>42.00</td>
      <td>42.00</td>
      <td>42.000000</td>
      <td>0.000000</td>
      <td>42.00</td>
      <td>8.312442e+07</td>
      <td>9.5</td>
      <td>9.165151</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.00</td>
      <td>141.55</td>
      <td>DDoS-ICMP_Flood</td>
    </tr>
    <tr>
      <th>34750</th>
      <td>0.000000</td>
      <td>54.00</td>
      <td>6.00</td>
      <td>64.00</td>
      <td>2.472561</td>
      <td>2.472561</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.00</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>1.00</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>567.00</td>
      <td>54.00</td>
      <td>54.00</td>
      <td>54.000000</td>
      <td>0.000000</td>
      <td>54.00</td>
      <td>8.331473e+07</td>
      <td>9.5</td>
      <td>10.392305</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.00</td>
      <td>141.55</td>
      <td>DDoS-PSHACK_Flood</td>
    </tr>
  </tbody>
</table>
</div>
</div>       
-  This is coutn plot of output columns with 34 classes      

![download34](https://github.com/Vivek7987/Enhancing-Network-Attack-Classification-through-Ensemble-Learning-Techniques/assets/111482462/1e5939c6-3687-452f-94ee-460827cddbf7)


-  ROC Curve of 8 classes
  
![download1](https://github.com/Vivek7987/Enhancing-Network-Attack-Classification-through-Ensemble-Learning-Techniques/assets/111482462/38a90269-2624-4f71-903c-ee6b6089ebcc)

-  Count Plot of 8 classes

![count8](https://github.com/Vivek7987/Enhancing-Network-Attack-Classification-through-Ensemble-Learning-Techniques/assets/111482462/de2865d1-2c9e-4ad3-938e-99eb2a5a5635)

-  Countplot of 2 class
  ![image](https://github.com/Vivek7987/Enhancing-Network-Attack-Classification-through-Ensemble-Learning-Techniques/assets/111482462/57236538-c2b3-4fdd-b44a-4439c5125167)

-  ROC curve of Different Model With 2 Class:
![image](https://github.com/Vivek7987/Enhancing-Network-Attack-Classification-through-Ensemble-Learning-Techniques/assets/111482462/ce9d5691-b1ab-4cca-a7dc-b6916b98af12)



-  Two Class Output(Ensembel learning):
  
![image](https://github.com/Vivek7987/Enhancing-Network-Attack-Classification-through-Ensemble-Learning-Techniques/assets/111482462/39b5b570-3e79-4a0f-9398-29f778d28620)


## Documentation     

Dataset Link: https://www.kaggle.com/datasets/madhavmalhotra/unb-cic-iot-dataset    
Paper which I take as help:  https://www.mdpi.com/1424-8220/23/13/5941

## Features
-  Multiclass Classification
-  Binary Classification
-  Ensemble Learning Techniques

# Feedback
For feedback, please reach out to paljivivek12@gmail.com      

# Github Profile - About Me     
Vivek Pal is a student at Amity University Madhya Pradesh, with a keen interest in machine learning and data science.     

# Installation
 1. Clone the repo
    ```bash
    git clone git@github.com:Vivek7987/Enhancing-Network-Attack-Classification-through-Ensemble-Learning-Techniques.git
 
   ```

