================================================================================  

SUMMARY:  

================================================================================  

Model: gemma3:12b
Sample count: 100
Total tokens: 5827
Mistakes: 42
Token accuracy: 0.9712
Precision: 0.8119
Recall: 0.6891
F1 Score: 0.7455
Total execution time: 149.95s

        prompt = f"""### ROLE
You are a Legal Document Analyst.

### TASK
Rewrite the provided text, wrapping every "Court" entity in <court> tags. Do not change any other text.
Use the counterexamples to do not extract similar text to them.
Use the examples of court entities below to detect the correct court entities.

### DEFINITION
A "Court" is a reference to a specific judicial body, tribunal, bench, or legal authority that adjudicates disputes.


### EXAMPLES OF COURT ENTITIES
For clarity, the following items are examples of the target pattern you are looking for:
<examples>
- Supreme Court
- Nagpur High Court
- Apex Court
- National Consumer Disputes Redresal Commission
- Court of Judicial Magistrate, Hanumangarh
- Constitution Bench
- KGF Court
- District Magistrate, Neemuch
- Narmada Tribunal
</examples>


### EXAMPLE
* Example Input: "The appeal was filed in the Nagpur High Court after the District Magistrate, Neemuch gave the order."
* Example Output: "The appeal was filed in the <court>Nagpur High Court</court> after the <court>District Magistrate, Neemuch</court> gave the order."

### COUNTEREXAMPLES
<counterexamples>
- the court has to
- the Tribunal has
- the Magistrate to

</counterexamples>

### TEXT
{text}

### FINAL RESPONSE
"""





[Mistake 27] Sample 70
Text: S.B.Civil First Appeal No. 16/1986-Madan Singh vs. Suraj Kanwar- S.B.Civil First Appeal No. 478/2006-Madan Singh vs. Rajendra Singh & Ors. Judgment dt:11/8/2011 1/32 In The High Court Of Judicature For Rajasthan At Jodhpur Judgment
Extracted targets: ['High Court']
Text with predictions vs ground truth: S.B.Civil First Appeal No. 16/1986-Madan Singh vs. Suraj Kanwar- S.B.Civil First Appeal No. 478/2006-Madan Singh vs. Rajendra Singh & Ors. Judgment dt:11/8/2011 1/32 In The High Court Of Judicature For Rajasthan At Jodhpur Judgment
  Token 31 'Of': FALSE NEGATIVE (predicted=False, truth=True)
  Token 32 'Judicature': FALSE NEGATIVE (predicted=False, truth=True)
  Token 33 'For': FALSE NEGATIVE (predicted=False, truth=True)
  Token 34 'Rajasthan': FALSE NEGATIVE (predicted=False, truth=True)
  Token 35 'At': FALSE NEGATIVE (predicted=False, truth=True)
  Token 36 'Jodhpur': FALSE NEGATIVE (predicted=False, truth=True)

[Mistake 28] Sample 71
Text: 1 Civil Revision No.105/2015 High Court Of Madhya Pradesh Bench At Gwalior Civil Revision No.105/2015 Petitioner....... Vijay Sood Vs. Respondents..... Kanak Devi and others -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- Shri N.K.Gupta, Sr. Advocate with Shri Sanjay Sharma, Advocate for the petitioner. Shri V.K.Bhardwaj, Sr. Advocate with Shri Anoop Gupta, Advocate for the respondent No.1. Date of hearing: 01/02/2016 Date of order: 29/03/2016 Whether approved for reporting: Yes Order
Extracted targets: ['High Court Of Madhya Pradesh']
Text with predictions vs ground truth: 1 Civil Revision No.105/2015 High Court Of Madhya Pradesh Bench At Gwalior Civil Revision No.105/2015 Petitioner....... Vijay Sood Vs. Respondents..... Kanak Devi and others -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- Shri N.K.Gupta, Sr. Advocate with Shri Sanjay Sharma, Advocate for the petitioner. Shri V.K.Bhardwaj, Sr. Advocate with Shri Anoop Gupta, Advocate for the respondent No.1. Date of hearing: 01/02/2016 Date of order: 29/03/2016 Whether approved for reporting: Yes Order
  Token 10 'Bench': FALSE NEGATIVE (predicted=False, truth=True)
  Token 11 'At': FALSE NEGATIVE (predicted=False, truth=True)
  Token 12 'Gwalior': FALSE NEGATIVE (predicted=False, truth=True)

[Mistake 29] Sample 75
Text: The two leading decisions are 8 Beng LR 433, a decision of this Court given in 1872 and ILR 35 Mad 1, a decision of the Madras High Court, given in 1910.
Extracted targets: ['Court', 'Madras High Court']
Text with predictions vs ground truth: The two leading decisions are 8 Beng LR 433, a decision of this Court given in 1872 and ILR 35 Mad 1, a decision of the Madras High Court, given in 1910.
  Token 15 'Court': FALSE POSITIVE (predicted=True, truth=False)

[Mistake 30] Sample 76
Text: Law laid down by the Supreme Court: - 18.
Extracted targets: ['Supreme Court']
Text with predictions vs ground truth: Law laid down by the Supreme Court : - 18.
  Token 8 ':': FALSE NEGATIVE (predicted=False, truth=True)
  Token 9 '-': FALSE NEGATIVE (predicted=False, truth=True)

[Mistake 31] Sample 77
Text: Reportable In The Supreme Court Of India Civil Appellate Jurisdiction Civil Appeal Nos. 2525-2516 Of 2013 (Arising out of S.L.P. (C) Nos.5752-53 of 2008 Rajesh Kumar & Ors. etc. …Appellants Versus State of Bihar & Ors. etc. …Respondents With Civil Appeal No. 2517 Of 2013 (Arising out of Slp (C) No.6456 of 2008) Abhishek Kumar & Ors. …Appellants Versus State of Bihar & Ors. …Respondents J U D G M E N T
Extracted targets: ['Supreme Court']
Text with predictions vs ground truth: Reportable In The Supreme Court Of India Civil Appellate Jurisdiction Civil Appeal Nos. 2525-2516 Of 2013 (Arising out of S.L.P. (C) Nos.5752-53 of 2008 Rajesh Kumar & Ors. etc. …Appellants Versus State of Bihar & Ors. etc. …Respondents With Civil Appeal No. 2517 Of 2013 (Arising out of Slp (C) No.6456 of 2008) Abhishek Kumar & Ors. …Appellants Versus State of Bihar & Ors. …Respondents J U D G M E N T
  Token 6 'Of': FALSE NEGATIVE (predicted=False, truth=True)
  Token 7 'India': FALSE NEGATIVE (predicted=False, truth=True)

[Mistake 32] Sample 78
Text: Reportable In The Supreme Court Of India Criminal Appellate Jurisdiction Criminal Appeal No. 148 of 2003 1 2 Dharam Pal & Ors. … Appellants Vs. 2 State Of Haryana & Anr. … Respondents With Criminal Appeal Nos. 865 of 2004, 1334 of 2005 and 537 of 2006 J U D G M E N T
Extracted targets: ['Supreme Court']
Text with predictions vs ground truth: Reportable In The Supreme Court Of India Criminal Appellate Jurisdiction Criminal Appeal No. 148 of 2003 1 2 Dharam Pal & Ors. … Appellants Vs. 2 State Of Haryana & Anr. … Respondents With Criminal Appeal Nos. 865 of 2004, 1334 of 2005 and 537 of 2006 J U D G M E N T
  Token 6 'Of': FALSE NEGATIVE (predicted=False, truth=True)
  Token 7 'India': FALSE NEGATIVE (predicted=False, truth=True)

[Mistake 33] Sample 79
Text: Under these circumstances, as per Section 3 of the Act, driver of the tanker lorry was having valid and effective driving licence, despite of that, the Tribunal has committed an error in fastening the liability on the owner of tanker lorry.
Extracted targets: ['Tribunal']
Text with predictions vs ground truth: Under these circumstances, as per Section 3 of the Act, driver of the tanker lorry was having valid and effective driving licence, despite of that, the Tribunal has committed an error in fastening the liability on the owner of tanker lorry.
  Token 31 'Tribunal': FALSE POSITIVE (predicted=True, truth=False)

[Mistake 34] Sample 82
Text: In The Court Of Sh. Pitamber Dutt; Adj (Central) -11, Delhi Suit No. 927/08 Unique I.D No. 02401C0517582007 1. Rajan Rattan S/o Sh. Sanjay Rattan 2. Hunny Rattan S/o Sh. Sanjay Rattan 3. Usha Rattan W/o Sh. Sanjay Rattan All Residents of House No. A-1/78, Sector-4, Rohini, Delhi....... P l a i n t i f f s Versus 1. Sh. Kunti Nandan Sharma S/o late Sh. Chunni Lal R/o L-86-A, Malviya Nagar, New Delhi 2. Smt. Jyoti W/o Sh. Rajesh Sharma House no. 12, Biharipur, Krolan, Bareilly, U.P....... D e f e n d a n t s Date of Institution of Suit: 19.05.2007 Date when reserved for orders: 10.12.2013 Date of Decision: 18.12.2013 Judgment
Extracted targets: ['The Court Of Sh. Pitamber Dutt']
Text with predictions vs ground truth: In The Court Of Sh . Pitamber Dutt ; Adj ( Central ) -11 , Delhi Suit No. 927/08 Unique I.D No. 02401C0517582007 1. Rajan Rattan S/o Sh. Sanjay Rattan 2. Hunny Rattan S/o Sh. Sanjay Rattan 3. Usha Rattan W/o Sh. Sanjay Rattan All Residents of House No. A-1/78, Sector-4, Rohini, Delhi....... P l a i n t i f f s Versus 1. Sh. Kunti Nandan Sharma S/o late Sh. Chunni Lal R/o L-86-A, Malviya Nagar, New Delhi 2. Smt. Jyoti W/o Sh. Rajesh Sharma House no. 12, Biharipur, Krolan, Bareilly, U.P....... D e f e n d a n t s Date of Institution of Suit: 19.05.2007 Date when reserved for orders: 10.12.2013 Date of Decision: 18.12.2013 Judgment
  Token 2 'The': FALSE POSITIVE (predicted=True, truth=False)
  Token 9 ';': FALSE NEGATIVE (predicted=False, truth=True)
  Token 10 'Adj': FALSE NEGATIVE (predicted=False, truth=True)
  Token 11 '(': FALSE NEGATIVE (predicted=False, truth=True)
  Token 12 'Central': FALSE NEGATIVE (predicted=False, truth=True)
  Token 13 ')': FALSE NEGATIVE (predicted=False, truth=True)
  Token 14 '-11': FALSE NEGATIVE (predicted=False, truth=True)
  Token 15 ',': FALSE NEGATIVE (predicted=False, truth=True)
  Token 16 'Delhi': FALSE NEGATIVE (predicted=False, truth=True)

[Mistake 35] Sample 83
Text: Reportable In The Supreme Court Of India Civil Appellate Jurisdiction Civil Appeal No. 1374 of 2008 Union of India.... Appellant Versus Ibrahim Uddin & Anr..... Respondents J U D G M E N T
Extracted targets: ['Supreme Court']
Text with predictions vs ground truth: Reportable In The Supreme Court Of India Civil Appellate Jurisdiction Civil Appeal No. 1374 of 2008 Union of India.... Appellant Versus Ibrahim Uddin & Anr..... Respondents J U D G M E N T
  Token 6 'Of': FALSE NEGATIVE (predicted=False, truth=True)
  Token 7 'India': FALSE NEGATIVE (predicted=False, truth=True)

[Mistake 36] Sample 87
Text: We are inclined to agree that the grant of a constitutional passport to the Supreme Court by the High Court is not a matter of easy insouciance but anxious advertence to the dual vital requirements built into Art. 133 (1) by specific amendment.
Extracted targets: ['Supreme Court', 'High Court']
Text with predictions vs ground truth: We are inclined to agree that the grant of a constitutional passport to the Supreme Court by the High Court is not a matter of easy insouciance but anxious advertence to the dual vital requirements built into Art. 133 (1) by specific amendment.
  Token 19 'High': FALSE POSITIVE (predicted=True, truth=False)
  Token 20 'Court': FALSE POSITIVE (predicted=True, truth=False)

[Mistake 37] Sample 89
Text: The Apex Court held that the trial Court, was right, in coming to the conclusion, that the accused were found in conscious possession of charas, as they had failed to explain, as to how they were travelling in a Car together, which was not a public vehicle.
Extracted targets: ['Apex Court', 'trial Court']
Text with predictions vs ground truth: The Apex Court held that the trial Court, was right, in coming to the conclusion, that the accused were found in conscious possession of charas, as they had failed to explain, as to how they were travelling in a Car together, which was not a public vehicle.
  Token 7 'trial': FALSE POSITIVE (predicted=True, truth=False)
  Token 8 'Court': FALSE POSITIVE (predicted=True, truth=False)

[Mistake 38] Sample 92
Text: Counsel appearing for respondents 4 and 5 referred to the decisions of this Court and the Supreme court which the Tribunal has relied on while passing the award and contended that the word'legal heirs'include illegitimate children also.
Extracted targets: ['Court', 'Supreme Court', 'Tribunal']
Text with predictions vs ground truth: Counsel appearing for respondents 4 and 5 referred to the decisions of this Court and the Supreme court which the Tribunal has relied on while passing the award and contended that the word'legal heirs'include illegitimate children also.
  Token 14 'Court': FALSE POSITIVE (predicted=True, truth=False)
  Token 17 'Supreme': FALSE NEGATIVE (predicted=False, truth=True)
  Token 18 'court': FALSE NEGATIVE (predicted=False, truth=True)
  Token 21 'Tribunal': FALSE POSITIVE (predicted=True, truth=False)

[Mistake 39] Sample 96
Text: 1 Reportable In The Supreme Court Of India Civil Appellate Jurisdiction Civil Appeal No. 1537 Of 2016 R. Janakiammal... Appellant Versus S.K. Kumarasamy (Deceased) Through Legal Representatives And Others... Respondents With Civil Appeal No.1538 Of 2016 S.R. Somasundaram And Another... Appellants Versus S.K. Kumarasamy (Deceased) Through Legal Representatives And Others... Respondents J U D G M E N T
Extracted targets: ['Supreme Court']
Text with predictions vs ground truth: 1 Reportable In The Supreme Court Of India Civil Appellate Jurisdiction Civil Appeal No. 1537 Of 2016 R. Janakiammal... Appellant Versus S.K. Kumarasamy (Deceased) Through Legal Representatives And Others... Respondents With Civil Appeal No.1538 Of 2016 S.R. Somasundaram And Another... Appellants Versus S.K. Kumarasamy (Deceased) Through Legal Representatives And Others... Respondents J U D G M E N T
  Token 7 'Of': FALSE NEGATIVE (predicted=False, truth=True)
  Token 8 'India': FALSE NEGATIVE (predicted=False, truth=True)

[Mistake 40] Sample 97
Text: 1 Reportable In The Supreme Court Of India Civil Original Jurisdiction Transferred Case (Civil) No. 245/2020 Lalit Kumar Jain ….Petitioner (S) Versus Union Of India & Ors. ….. Respondent (S) With W.P. (C) No. 117/2021, W.P. (C) No. 1371/2020, W.P. (C) No. 1420/2020, W.P. (C) No. 1353/2020, T.P. (C) No. 1252/2020, W.P. (C) No. 1276/2020, W.P. (C) No. 1287/2020, T.P. (C) No. 1285/2020, T.P. (C) No. 1325/2020, W.P. (C) No. 1364/2020, T.C. (C) No. 257/2020, W.P. (C) No. 1434/2020, W.P. (C) No. 38/2021, W.P. (C) No. 1419/2020, T.P. (C) No. 1202/2020, T.P. (C) No. 1220/2020, T.P. (C) No. 1203/2020, T.P. (C) No. 1193/2020, T.P. (C) No. 1196/2020, T.P. (C) No. 1289/2020, T.P. (C) No. 1323/2020, T.P. (C) No. 1333/2020, T.P. (C) No. 1292/2020, T.P. (C) No. 1299/2020, T.P. (C) No. 1331/2020, W.P. (C) No. 1342/2020, T.P. (C) No. 1339/2020, W.P. (C) No. 1348/2020, W.P. (C) No. 1344/2020, W.P. (C) No. 1343/2020, T.C. (C) No. 250/2020, T.C. (C) No. 251/2020, T.C. (C) No. 247/2020, T.C. (C) No. 253/2020, T.C. (C) No. 252/2020, T.C. (C) No. 248/2020, T.C. (C) No. 254/2020, T.C. (C) No. 246/2020, T.C. (C) No. 256/2020, T.C. (C) No. 249/2020, T.C. (C) No. 255/2020, W.P. (C) No. 62/2021, W.P. (C) No. 32/2021, W.P. (C) No. 106/2021, W.P. (C) No. 97/2021, W.P. (C) No. 142/2021, W.P. (C) No. 135/2021, W.P. (C) No. 131/2021, W.P. (C) No. 122/2021, W.P. (C) No. 138/2021, W.P. (C) No. 146/2021, W.P. (C) No. 207/2021, W.P. (C) No. 160/2021, W.P. (C) No. 168/2021, W.P. (C) No. 205/2021, W.P. (C) No. 209/2021, W.P. (C) No. 194/2021, W.P. (C) No. 187/2021, W.P. (C) No. 180/2021, W.P. (C) No. 182/2021, W.P. (C) No. 203/2021, W.P. (C) No. 220/2021, W.P. (C) No. 229/2021, W.P. (C) No. 217/2021, W.P. (C) No. 221/2021, W.P. (C) No. 225/2021, W.P. Signature Not Verified (C) No. 239/2021, W.P. (C) No. 240/2021, W.P. (C) No. 228/2021, W.P. (C) No. 224/2021, Digitally signed by Jayant Kumar Arora Date: 2021.05.21 13:36:48 Ist Reason: W.P. (C) No. 234/2021, W.P. (C) No. 260/2021 and W.P. (C) No. 262/2021, W.P. (C) No. 283/2021. 2 Judgment
Extracted targets: ['Supreme Court']
Text with predictions vs ground truth: 1 Reportable In The Supreme Court Of India Civil Original Jurisdiction Transferred Case (Civil) No. 245/2020 Lalit Kumar Jain ….Petitioner (S) Versus Union Of India & Ors. ….. Respondent (S) With W.P. (C) No. 117/2021, W.P. (C) No. 1371/2020, W.P. (C) No. 1420/2020, W.P. (C) No. 1353/2020, T.P. (C) No. 1252/2020, W.P. (C) No. 1276/2020, W.P. (C) No. 1287/2020, T.P. (C) No. 1285/2020, T.P. (C) No. 1325/2020, W.P. (C) No. 1364/2020, T.C. (C) No. 257/2020, W.P. (C) No. 1434/2020, W.P. (C) No. 38/2021, W.P. (C) No. 1419/2020, T.P. (C) No. 1202/2020, T.P. (C) No. 1220/2020, T.P. (C) No. 1203/2020, T.P. (C) No. 1193/2020, T.P. (C) No. 1196/2020, T.P. (C) No. 1289/2020, T.P. (C) No. 1323/2020, T.P. (C) No. 1333/2020, T.P. (C) No. 1292/2020, T.P. (C) No. 1299/2020, T.P. (C) No. 1331/2020, W.P. (C) No. 1342/2020, T.P. (C) No. 1339/2020, W.P. (C) No. 1348/2020, W.P. (C) No. 1344/2020, W.P. (C) No. 1343/2020, T.C. (C) No. 250/2020, T.C. (C) No. 251/2020, T.C. (C) No. 247/2020, T.C. (C) No. 253/2020, T.C. (C) No. 252/2020, T.C. (C) No. 248/2020, T.C. (C) No. 254/2020, T.C. (C) No. 246/2020, T.C. (C) No. 256/2020, T.C. (C) No. 249/2020, T.C. (C) No. 255/2020, W.P. (C) No. 62/2021, W.P. (C) No. 32/2021, W.P. (C) No. 106/2021, W.P. (C) No. 97/2021, W.P. (C) No. 142/2021, W.P. (C) No. 135/2021, W.P. (C) No. 131/2021, W.P. (C) No. 122/2021, W.P. (C) No. 138/2021, W.P. (C) No. 146/2021, W.P. (C) No. 207/2021, W.P. (C) No. 160/2021, W.P. (C) No. 168/2021, W.P. (C) No. 205/2021, W.P. (C) No. 209/2021, W.P. (C) No. 194/2021, W.P. (C) No. 187/2021, W.P. (C) No. 180/2021, W.P. (C) No. 182/2021, W.P. (C) No. 203/2021, W.P. (C) No. 220/2021, W.P. (C) No. 229/2021, W.P. (C) No. 217/2021, W.P. (C) No. 221/2021, W.P. (C) No. 225/2021, W.P. Signature Not Verified (C) No. 239/2021, W.P. (C) No. 240/2021, W.P. (C) No. 228/2021, W.P. (C) No. 224/2021, Digitally signed by Jayant Kumar Arora Date: 2021.05.21 13:36:48 Ist Reason: W.P. (C) No. 234/2021, W.P. (C) No. 260/2021 and W.P. (C) No. 262/2021, W.P. (C) No. 283/2021. 2 Judgment
  Token 7 'Of': FALSE NEGATIVE (predicted=False, truth=True)
  Token 8 'India': FALSE NEGATIVE (predicted=False, truth=True)

[Mistake 41] Sample 99
Text: If the Supreme Court had declared that Section 20 as intra vires the matter would have come to an end so far as the High Courts are concerned.
Extracted targets: ['Supreme Court', 'High Courts']
Text with predictions vs ground truth: If the Supreme Court had declared that Section 20 as intra vires the matter would have come to an end so far as the High Courts are concerned.
  Token 25 'High': FALSE POSITIVE (predicted=True, truth=False)
  Token 26 'Courts': FALSE POSITIVE (predicted=True, truth=False)

[Mistake 42] Sample 100
Text: Reportable In The Supreme Court Of India Criminal Appellate Jurisdiction Criminal Appeal No. 2021 Of 2008 [arising out of Slp (Criminal) No. 1712 of 2004] M/S. Harman Electronics (P) Ltd. & Anr.... Appellants Versus M/S. National Panasonic India Ltd.... Respondent Judgment
Extracted targets: ['Supreme Court']
Text with predictions vs ground truth: Reportable In The Supreme Court Of India Criminal Appellate Jurisdiction Criminal Appeal No. 2021 Of 2008 [arising out of Slp (Criminal) No. 1712 of 2004] M/S. Harman Electronics (P) Ltd. & Anr.... Appellants Versus M/S. National Panasonic India Ltd.... Respondent Judgment
  Token 6 'Of': FALSE NEGATIVE (predicted=False, truth=True)
  Token 7 'India': FALSE NEGATIVE (predicted=False, truth=True)



================================================================================  

SUMMARY:  

================================================================================  

Model: gemma3:27b-cloud
Sample count: 100
Total tokens: 5827
Mistakes: 36
Token accuracy: 0.9751
Precision: 0.8813
Recall: 0.6863
F1 Score: 0.7717
Total execution time: 288.11s
Average time per text: 2.88s






        prompt = f"""### ROLE
You are a Legal Document Analyst.

### TASK
Rewrite the provided text, wrapping every "Court" entity in <court> tags. Do not change any other text.
Use the counterexamples to do not extract similar text to them.
Use the examples of court entities below to detect the correct court entities.

### DEFINITION
A "Court" is a reference to a specific judicial body, tribunal, bench, or legal authority that adjudicates disputes.


### EXAMPLES OF COURT ENTITIES
For clarity, the following items are examples of the target pattern you are looking for:
<examples>
- Supreme Court
- Nagpur High Court
- Apex Court
- National Consumer Disputes Redresal Commission
- Court of Judicial Magistrate, Hanumangarh
- Constitution Bench
- KGF Court
- District Magistrate, Neemuch
- Narmada Tribunal
</examples>


### EXAMPLE
* Example Input: "The appeal was filed in the Nagpur High Court after the District Magistrate, Neemuch gave the order."
* Example Output: "The appeal was filed in the <court>Nagpur High Court</court> after the <court>District Magistrate, Neemuch</court> gave the order."

### COUNTEREXAMPLES
<counterexamples>
- the court has to
- the Tribunal has
- the Magistrate to

</counterexamples>

### TEXT
{text}

### FINAL RESPONSE
"""





### Mistake 23 - Sample 75

**Text:** The two leading decisions are 8 Beng LR 433, a decision of this Court given in 1872 and ILR 35 Mad 1, a decision of the Madras High Court, given in 1910.

**Extracted targets:** ['Court', 'Madras High Court']

**Text with predictions vs ground truth:**

The two leading decisions are 8 Beng LR 433, a decision of this <span style="color: #ff8800; font-weight: bold;">Court</span> given in 1872 and ILR 35 Mad 1, a decision of the <span style="color: #00ff00; font-weight: bold;">Madras</span> <span style="color: #00ff00; font-weight: bold;">High</span> <span style="color: #00ff00; font-weight: bold;">Court</span>, given in 1910.

**Mistake details:**
  - Token 15 'Court': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 24 - Sample 76

**Text:** Law laid down by the Supreme Court: - 18.

**Extracted targets:** ['Supreme Court']

**Text with predictions vs ground truth:**

Law laid down by the <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #ff0000; font-weight: bold;">:</span> <span style="color: #ff0000; font-weight: bold;">-</span> 18.

**Mistake details:**
  - Token 8 ':': FALSE NEGATIVE (predicted=False, truth=True)  - Token 9 '-': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 25 - Sample 77

**Text:** Reportable In The Supreme Court Of India Civil Appellate Jurisdiction Civil Appeal Nos. 2525-2516 Of 2013 (Arising out of S.L.P. (C) Nos.5752-53 of 2008 Rajesh Kumar & Ors. etc. …Appellants Versus State of Bihar & Ors. etc. …Respondents With Civil Appeal No. 2517 Of 2013 (Arising out of Slp (C) No.6456 of 2008) Abhishek Kumar & Ors. …Appellants Versus State of Bihar & Ors. …Respondents J U D G M E N T

**Extracted targets:** ['Supreme Court']

**Text with predictions vs ground truth:**

Reportable In The <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #ff0000; font-weight: bold;">Of</span> <span style="color: #ff0000; font-weight: bold;">India</span> Civil Appellate Jurisdiction Civil Appeal Nos. 2525-2516 Of 2013 (Arising out of S.L.P. (C) Nos.5752-53 of 2008 Rajesh Kumar &amp; Ors. etc. …Appellants Versus State of Bihar &amp; Ors. etc. …Respondents With Civil Appeal No. 2517 Of 2013 (Arising out of Slp (C) No.6456 of 2008) Abhishek Kumar &amp; Ors. …Appellants Versus State of Bihar &amp; Ors. …Respondents J U D G M E N T

**Mistake details:**
  - Token 6 'Of': FALSE NEGATIVE (predicted=False, truth=True)  - Token 7 'India': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 26 - Sample 78

**Text:** Reportable In The Supreme Court Of India Criminal Appellate Jurisdiction Criminal Appeal No. 148 of 2003 1 2 Dharam Pal & Ors. … Appellants Vs. 2 State Of Haryana & Anr. … Respondents With Criminal Appeal Nos. 865 of 2004, 1334 of 2005 and 537 of 2006 J U D G M E N T

**Extracted targets:** ['Supreme Court']

**Text with predictions vs ground truth:**

Reportable In The <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #ff0000; font-weight: bold;">Of</span> <span style="color: #ff0000; font-weight: bold;">India</span> Criminal Appellate Jurisdiction Criminal Appeal No. 148 of 2003 1 2 Dharam Pal &amp; Ors. … Appellants Vs. 2 State Of Haryana &amp; Anr. … Respondents With Criminal Appeal Nos. 865 of 2004, 1334 of 2005 and 537 of 2006 J U D G M E N T

**Mistake details:**
  - Token 6 'Of': FALSE NEGATIVE (predicted=False, truth=True)  - Token 7 'India': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 27 - Sample 79

**Text:** Under these circumstances, as per Section 3 of the Act, driver of the tanker lorry was having valid and effective driving licence, despite of that, the Tribunal has committed an error in fastening the liability on the owner of tanker lorry.

**Extracted targets:** ['Tribunal']

**Text with predictions vs ground truth:**

Under these circumstances, as per Section 3 of the Act, driver of the tanker lorry was having valid and effective driving licence, despite of that, the <span style="color: #ff8800; font-weight: bold;">Tribunal</span> has committed an error in fastening the liability on the owner of tanker lorry.

**Mistake details:**
  - Token 31 'Tribunal': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 28 - Sample 82

**Text:** In The Court Of Sh. Pitamber Dutt; Adj (Central) -11, Delhi Suit No. 927/08 Unique I.D No. 02401C0517582007 1. Rajan Rattan S/o Sh. Sanjay Rattan 2. Hunny Rattan S/o Sh. Sanjay Rattan 3. Usha Rattan W/o Sh. Sanjay Rattan All Residents of House No. A-1/78, Sector-4, Rohini, Delhi....... P l a i n t i f f s Versus 1. Sh. Kunti Nandan Sharma S/o late Sh. Chunni Lal R/o L-86-A, Malviya Nagar, New Delhi 2. Smt. Jyoti W/o Sh. Rajesh Sharma House no. 12, Biharipur, Krolan, Bareilly, U.P....... D e f e n d a n t s Date of Institution of Suit: 19.05.2007 Date when reserved for orders: 10.12.2013 Date of Decision: 18.12.2013 Judgment

**Extracted targets:** ['Court']

**Text with predictions vs ground truth:**

In The <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #ff0000; font-weight: bold;">Of</span> <span style="color: #ff0000; font-weight: bold;">Sh</span> <span style="color: #ff0000; font-weight: bold;">.</span> <span style="color: #ff0000; font-weight: bold;">Pitamber</span> <span style="color: #ff0000; font-weight: bold;">Dutt</span> <span style="color: #ff0000; font-weight: bold;">;</span> <span style="color: #ff0000; font-weight: bold;">Adj</span> <span style="color: #ff0000; font-weight: bold;">(</span> <span style="color: #ff0000; font-weight: bold;">Central</span> <span style="color: #ff0000; font-weight: bold;">)</span> <span style="color: #ff0000; font-weight: bold;">-11</span> <span style="color: #ff0000; font-weight: bold;">,</span> <span style="color: #ff0000; font-weight: bold;">Delhi</span> Suit No. 927/08 Unique I.D No. 02401C0517582007 1. Rajan Rattan S/o Sh. Sanjay Rattan 2. Hunny Rattan S/o Sh. Sanjay Rattan 3. Usha Rattan W/o Sh. Sanjay Rattan All Residents of House No. A-1/78, Sector-4, Rohini, Delhi....... P l a i n t i f f s Versus 1. Sh. Kunti Nandan Sharma S/o late Sh. Chunni Lal R/o L-86-A, Malviya Nagar, New Delhi 2. Smt. Jyoti W/o Sh. Rajesh Sharma House no. 12, Biharipur, Krolan, Bareilly, U.P....... D e f e n d a n t s Date of Institution of Suit: 19.05.2007 Date when reserved for orders: 10.12.2013 Date of Decision: 18.12.2013 Judgment

**Mistake details:**
  - Token 4 'Of': FALSE NEGATIVE (predicted=False, truth=True)  - Token 5 'Sh': FALSE NEGATIVE (predicted=False, truth=True)  - Token 6 '.': FALSE NEGATIVE (predicted=False, truth=True)  - Token 7 'Pitamber': FALSE NEGATIVE (predicted=False, truth=True)  - Token 8 'Dutt': FALSE NEGATIVE (predicted=False, truth=True)  - Token 9 ';': FALSE NEGATIVE (predicted=False, truth=True)  - Token 10 'Adj': FALSE NEGATIVE (predicted=False, truth=True)  - Token 11 '(': FALSE NEGATIVE (predicted=False, truth=True)  - Token 12 'Central': FALSE NEGATIVE (predicted=False, truth=True)  - Token 13 ')': FALSE NEGATIVE (predicted=False, truth=True)  - Token 14 '-11': FALSE NEGATIVE (predicted=False, truth=True)  - Token 15 ',': FALSE NEGATIVE (predicted=False, truth=True)  - Token 16 'Delhi': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 29 - Sample 83

**Text:** Reportable In The Supreme Court Of India Civil Appellate Jurisdiction Civil Appeal No. 1374 of 2008 Union of India.... Appellant Versus Ibrahim Uddin & Anr..... Respondents J U D G M E N T

**Extracted targets:** ['Supreme Court']

**Text with predictions vs ground truth:**

Reportable In The <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #ff0000; font-weight: bold;">Of</span> <span style="color: #ff0000; font-weight: bold;">India</span> Civil Appellate Jurisdiction Civil Appeal No. 1374 of 2008 Union of India.... Appellant Versus Ibrahim Uddin &amp; Anr..... Respondents J U D G M E N T

**Mistake details:**
  - Token 6 'Of': FALSE NEGATIVE (predicted=False, truth=True)  - Token 7 'India': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 30 - Sample 87

**Text:** We are inclined to agree that the grant of a constitutional passport to the Supreme Court by the High Court is not a matter of easy insouciance but anxious advertence to the dual vital requirements built into Art. 133 (1) by specific amendment.

**Extracted targets:** ['Supreme Court', 'High Court']

**Text with predictions vs ground truth:**

We are inclined to agree that the grant of a constitutional passport to the <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> by the <span style="color: #ff8800; font-weight: bold;">High</span> <span style="color: #ff8800; font-weight: bold;">Court</span> is not a matter of easy insouciance but anxious advertence to the dual vital requirements built into Art. 133 (1) by specific amendment.

**Mistake details:**
  - Token 19 'High': FALSE POSITIVE (predicted=True, truth=False)  - Token 20 'Court': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 31 - Sample 90

**Text:** CCA is not one of the specified Acts and does not come within the sweep of section 6 of the said Act under which jurisdiction has been conferred on the LRTT.

**Extracted targets:** []

**Text with predictions vs ground truth:**

CCA is not one of the specified Acts and does not come within the sweep of section 6 of the said Act under which jurisdiction has been conferred on the <span style="color: #ff0000; font-weight: bold;">LRTT</span>.

**Mistake details:**
  - Token 31 'LRTT': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 32 - Sample 92

**Text:** Counsel appearing for respondents 4 and 5 referred to the decisions of this Court and the Supreme court which the Tribunal has relied on while passing the award and contended that the word'legal heirs'include illegitimate children also.

**Extracted targets:** ['Court', 'Supreme Court']

**Text with predictions vs ground truth:**

Counsel appearing for respondents 4 and 5 referred to the decisions of this <span style="color: #ff8800; font-weight: bold;">Court</span> and the <span style="color: #ff0000; font-weight: bold;">Supreme</span> <span style="color: #ff0000; font-weight: bold;">court</span> which the Tribunal has relied on while passing the award and contended that the word &#x27;legal heirs &#x27; include illegitimate children also.

**Mistake details:**
  - Token 14 'Court': FALSE POSITIVE (predicted=True, truth=False)  - Token 17 'Supreme': FALSE NEGATIVE (predicted=False, truth=True)  - Token 18 'court': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 33 - Sample 96

**Text:** 1 Reportable In The Supreme Court Of India Civil Appellate Jurisdiction Civil Appeal No. 1537 Of 2016 R. Janakiammal... Appellant Versus S.K. Kumarasamy (Deceased) Through Legal Representatives And Others... Respondents With Civil Appeal No.1538 Of 2016 S.R. Somasundaram And Another... Appellants Versus S.K. Kumarasamy (Deceased) Through Legal Representatives And Others... Respondents J U D G M E N T

**Extracted targets:** ['Supreme Court']

**Text with predictions vs ground truth:**

1 Reportable In The <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #ff0000; font-weight: bold;">Of</span> <span style="color: #ff0000; font-weight: bold;">India</span> Civil Appellate Jurisdiction Civil Appeal No. 1537 Of 2016 R. Janakiammal... Appellant Versus S.K. Kumarasamy (Deceased) Through Legal Representatives And Others... Respondents With Civil Appeal No.1538 Of 2016 S.R. Somasundaram And Another... Appellants Versus S.K. Kumarasamy (Deceased) Through Legal Representatives And Others... Respondents J U D G M E N T

**Mistake details:**
  - Token 7 'Of': FALSE NEGATIVE (predicted=False, truth=True)  - Token 8 'India': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 34 - Sample 97

**Text:** 1 Reportable In The Supreme Court Of India Civil Original Jurisdiction Transferred Case (Civil) No. 245/2020 Lalit Kumar Jain ….Petitioner (S) Versus Union Of India & Ors. ….. Respondent (S) With W.P. (C) No. 117/2021, W.P. (C) No. 1371/2020, W.P. (C) No. 1420/2020, W.P. (C) No. 1353/2020, T.P. (C) No. 1252/2020, W.P. (C) No. 1276/2020, W.P. (C) No. 1287/2020, T.P. (C) No. 1285/2020, T.P. (C) No. 1325/2020, W.P. (C) No. 1364/2020, T.C. (C) No. 257/2020, W.P. (C) No. 1434/2020, W.P. (C) No. 38/2021, W.P. (C) No. 1419/2020, T.P. (C) No. 1202/2020, T.P. (C) No. 1220/2020, T.P. (C) No. 1203/2020, T.P. (C) No. 1193/2020, T.P. (C) No. 1196/2020, T.P. (C) No. 1289/2020, T.P. (C) No. 1323/2020, T.P. (C) No. 1333/2020, T.P. (C) No. 1292/2020, T.P. (C) No. 1299/2020, T.P. (C) No. 1331/2020, W.P. (C) No. 1342/2020, T.P. (C) No. 1339/2020, W.P. (C) No. 1348/2020, W.P. (C) No. 1344/2020, W.P. (C) No. 1343/2020, T.C. (C) No. 250/2020, T.C. (C) No. 251/2020, T.C. (C) No. 247/2020, T.C. (C) No. 253/2020, T.C. (C) No. 252/2020, T.C. (C) No. 248/2020, T.C. (C) No. 254/2020, T.C. (C) No. 246/2020, T.C. (C) No. 256/2020, T.C. (C) No. 249/2020, T.C. (C) No. 255/2020, W.P. (C) No. 62/2021, W.P. (C) No. 32/2021, W.P. (C) No. 106/2021, W.P. (C) No. 97/2021, W.P. (C) No. 142/2021, W.P. (C) No. 135/2021, W.P. (C) No. 131/2021, W.P. (C) No. 122/2021, W.P. (C) No. 138/2021, W.P. (C) No. 146/2021, W.P. (C) No. 207/2021, W.P. (C) No. 160/2021, W.P. (C) No. 168/2021, W.P. (C) No. 205/2021, W.P. (C) No. 209/2021, W.P. (C) No. 194/2021, W.P. (C) No. 187/2021, W.P. (C) No. 180/2021, W.P. (C) No. 182/2021, W.P. (C) No. 203/2021, W.P. (C) No. 220/2021, W.P. (C) No. 229/2021, W.P. (C) No. 217/2021, W.P. (C) No. 221/2021, W.P. (C) No. 225/2021, W.P. Signature Not Verified (C) No. 239/2021, W.P. (C) No. 240/2021, W.P. (C) No. 228/2021, W.P. (C) No. 224/2021, Digitally signed by Jayant Kumar Arora Date: 2021.05.21 13:36:48 Ist Reason: W.P. (C) No. 234/2021, W.P. (C) No. 260/2021 and W.P. (C) No. 262/2021, W.P. (C) No. 283/2021. 2 Judgment

**Extracted targets:** ['Supreme Court']

**Text with predictions vs ground truth:**

1 Reportable In The <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #ff0000; font-weight: bold;">Of</span> <span style="color: #ff0000; font-weight: bold;">India</span> Civil Original Jurisdiction Transferred Case (Civil) No. 245/2020 Lalit Kumar Jain ….Petitioner (S) Versus Union Of India &amp; Ors. ….. Respondent (S) With W.P. (C) No. 117/2021, W.P. (C) No. 1371/2020, W.P. (C) No. 1420/2020, W.P. (C) No. 1353/2020, T.P. (C) No. 1252/2020, W.P. (C) No. 1276/2020, W.P. (C) No. 1287/2020, T.P. (C) No. 1285/2020, T.P. (C) No. 1325/2020, W.P. (C) No. 1364/2020, T.C. (C) No. 257/2020, W.P. (C) No. 1434/2020, W.P. (C) No. 38/2021, W.P. (C) No. 1419/2020, T.P. (C) No. 1202/2020, T.P. (C) No. 1220/2020, T.P. (C) No. 1203/2020, T.P. (C) No. 1193/2020, T.P. (C) No. 1196/2020, T.P. (C) No. 1289/2020, T.P. (C) No. 1323/2020, T.P. (C) No. 1333/2020, T.P. (C) No. 1292/2020, T.P. (C) No. 1299/2020, T.P. (C) No. 1331/2020, W.P. (C) No. 1342/2020, T.P. (C) No. 1339/2020, W.P. (C) No. 1348/2020, W.P. (C) No. 1344/2020, W.P. (C) No. 1343/2020, T.C. (C) No. 250/2020, T.C. (C) No. 251/2020, T.C. (C) No. 247/2020, T.C. (C) No. 253/2020, T.C. (C) No. 252/2020, T.C. (C) No. 248/2020, T.C. (C) No. 254/2020, T.C. (C) No. 246/2020, T.C. (C) No. 256/2020, T.C. (C) No. 249/2020, T.C. (C) No. 255/2020, W.P. (C) No. 62/2021, W.P. (C) No. 32/2021, W.P. (C) No. 106/2021, W.P. (C) No. 97/2021, W.P. (C) No. 142/2021, W.P. (C) No. 135/2021, W.P. (C) No. 131/2021, W.P. (C) No. 122/2021, W.P. (C) No. 138/2021, W.P. (C) No. 146/2021, W.P. (C) No. 207/2021, W.P. (C) No. 160/2021, W.P. (C) No. 168/2021, W.P. (C) No. 205/2021, W.P. (C) No. 209/2021, W.P. (C) No. 194/2021, W.P. (C) No. 187/2021, W.P. (C) No. 180/2021, W.P. (C) No. 182/2021, W.P. (C) No. 203/2021, W.P. (C) No. 220/2021, W.P. (C) No. 229/2021, W.P. (C) No. 217/2021, W.P. (C) No. 221/2021, W.P. (C) No. 225/2021, W.P. Signature Not Verified (C) No. 239/2021, W.P. (C) No. 240/2021, W.P. (C) No. 228/2021, W.P. (C) No. 224/2021, Digitally signed by Jayant Kumar Arora Date: 2021.05.21 13:36:48 Ist Reason: W.P. (C) No. 234/2021, W.P. (C) No. 260/2021 and W.P. (C) No. 262/2021, W.P. (C) No. 283/2021. 2 Judgment

**Mistake details:**
  - Token 7 'Of': FALSE NEGATIVE (predicted=False, truth=True)  - Token 8 'India': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 35 - Sample 99

**Text:** If the Supreme Court had declared that Section 20 as intra vires the matter would have come to an end so far as the High Courts are concerned.

**Extracted targets:** ['Supreme Court', 'High Courts']

**Text with predictions vs ground truth:**

If the <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> had declared that Section 20 as intra vires the matter would have come to an end so far as the <span style="color: #ff8800; font-weight: bold;">High</span> <span style="color: #ff8800; font-weight: bold;">Courts</span> are concerned.

**Mistake details:**
  - Token 25 'High': FALSE POSITIVE (predicted=True, truth=False)  - Token 26 'Courts': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 36 - Sample 100

**Text:** Reportable In The Supreme Court Of India Criminal Appellate Jurisdiction Criminal Appeal No. 2021 Of 2008 [arising out of Slp (Criminal) No. 1712 of 2004] M/S. Harman Electronics (P) Ltd. & Anr.... Appellants Versus M/S. National Panasonic India Ltd.... Respondent Judgment

**Extracted targets:** ['Supreme Court']

**Text with predictions vs ground truth:**

Reportable In The <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #ff0000; font-weight: bold;">Of</span> <span style="color: #ff0000; font-weight: bold;">India</span> Criminal Appellate Jurisdiction Criminal Appeal No. 2021 Of 2008 [arising out of Slp (Criminal) No. 1712 of 2004] M/S. Harman Electronics (P) Ltd. &amp; Anr.... Appellants Versus M/S. National Panasonic India Ltd.... Respondent Judgment

**Mistake details:**
  - Token 6 'Of': FALSE NEGATIVE (predicted=False, truth=True)  - Token 7 'India': FALSE NEGATIVE (predicted=False, truth=True)




================================================================================  

SUMMARY:  

================================================================================  

Model: gemma3:12b
Sample count: 100
Total tokens: 5827
Mistakes: 26
Token accuracy: 0.9760
Precision: 0.8201
Recall: 0.7787
F1 Score: 0.7989
Total execution time: 149.39s
Average time per text: 1.49s



        prompt = f"""### ROLE
You are a Legal Document Analyst.

### TASK
Rewrite the provided text, wrapping every "Court" entity in <court> tags. Do not change any other text.
Use the counterexamples to do not extract similar text to them.
Use the examples of court entities below to detect the correct court entities.

### DEFINITION
A "Court" is a reference to a specific judicial body, tribunal, bench, or legal authority that adjudicates disputes.


### EXAMPLES OF COURT ENTITIES
For clarity, the following items are examples of the target pattern you are looking for:
<examples>
- Supreme Court of India
- Nagpur High Court
- Apex Court
- National Consumer Disputes Redresal Commission
- Court of Judicial Magistrate, Hanumangarh
- Constitution Bench
- KGF Court
- District Magistrate, Neemuch
- Narmada Tribunal
</examples>


### EXAMPLE
* Example Input: "The appeal was filed in the Nagpur High Court after the District Magistrate, Neemuch gave the order."
* Example Output: "The appeal was filed in the <court>Nagpur High Court</court> after the <court>District Magistrate, Neemuch</court> gave the order."

### COUNTEREXAMPLES
<counterexamples>
- the court has to
- the Tribunal has
- the Magistrate to

</counterexamples>

### TEXT
{text}

### FINAL RESPONSE
"""



**Color legend:** <span style="color: #00ff00; font-weight: bold;">Green</span>=True Positive, <span style="color: #ff8800; font-weight: bold;">Orange</span>=False Positive, <span style="color: #ff0000; font-weight: bold;">Red</span>=False Negative

### Mistake 1 - Sample 3

**Text:** To sum up, the rationale given in Smt. Santosh (supra) is that the liability to pay compensation under the MACT is based on tort i.e. general principle of estimating damages, i.e., balancing of what is the loss to the claimants of the future pecuniary benefits that would accrue to a person if he would not have died, with the pecuniary advantage from whichever source it comes.

**Extracted targets:** []

**Text with predictions vs ground truth:**

To sum up, the rationale given in Smt. Santosh (supra) is that the liability to pay compensation under the <span style="color: #ff0000; font-weight: bold;">MACT</span> is based on tort i.e. general principle of estimating damages, i.e., balancing of what is the loss to the claimants of the future pecuniary benefits that would accrue to a person if he would not have died, with the pecuniary advantage from whichever source it comes.

**Mistake details:**
  - Token 24 'MACT': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 2 - Sample 9

**Text:** In our opinion, tlierefore,''t.t__ie Courts of Gujarat andJAndhraj a're: _j_ right and

**Extracted targets:** ['Courts of Gujarat', 'Andhra']

**Text with predictions vs ground truth:**

In our opinion, tlierefore, &#x27;&#x27; t.t__ie <span style="color: #00ff00; font-weight: bold;">Courts</span> <span style="color: #00ff00; font-weight: bold;">of</span> <span style="color: #00ff00; font-weight: bold;">Gujarat</span> <span style="color: #ff8800; font-weight: bold;">andJAndhraj</span> a &#x27;re: _j_ right and

**Mistake details:**
  - Token 12 'andJAndhraj': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 3 - Sample 10

**Text:** Sc No.122/2013: Fir No.146/2013: Ps Ashok Vihar: State V/s Sundar Dod: 23.04.2015 In The Court Of Vinod Yadav: Addl. Sessions Judge­01: (North­West): Rohini District Courts: New Delhi (Sessions Case No.122/2013) Unique Identification No.: 02404R0195112013 State V/s Sunder Fir No.: 146/2013 U/s: 354 Ipc r/w Section 8 & 12 of Pocso Act, 2012 P.S.: Ashok Vihar State V/s Sundar, S/o Shri Raghu Raj, R/o Village Kanapar, Ps Bas Gav, District Gorakhpur, Uttar Pradesh. Present Address: Wp­437, Wazirpur, Delhi. Date of institution of case: 07.08.2013 Date of arguments: 04.04.2015 Date of pronouncement of judgment: 23.04.2015 J U D G M E N T

**Extracted targets:** ['Court', 'Rohini District Courts']

**Text with predictions vs ground truth:**

Sc No.122/2013: Fir No.146/2013: Ps Ashok Vihar: State V/s Sundar Dod: 23.04.2015 In The <span style="color: #ff8800; font-weight: bold;">Court</span> Of Vinod Yadav: <span style="color: #ff0000; font-weight: bold;">Addl</span> <span style="color: #ff0000; font-weight: bold;">.</span> <span style="color: #ff0000; font-weight: bold;">Sessions</span> <span style="color: #ff0000; font-weight: bold;">Judge­01</span> <span style="color: #ff0000; font-weight: bold;">:</span> <span style="color: #ff0000; font-weight: bold;">(</span> <span style="color: #ff0000; font-weight: bold;">North­West</span> <span style="color: #ff0000; font-weight: bold;">)</span> <span style="color: #ff0000; font-weight: bold;">:</span> <span style="color: #00ff00; font-weight: bold;">Rohini</span> <span style="color: #00ff00; font-weight: bold;">District</span> <span style="color: #00ff00; font-weight: bold;">Courts</span> <span style="color: #ff0000; font-weight: bold;">:</span> <span style="color: #ff0000; font-weight: bold;">New</span> <span style="color: #ff0000; font-weight: bold;">Delhi</span> (Sessions Case No.122/2013) Unique Identification No.: 02404R0195112013 State V/s Sunder Fir No.: 146/2013 U/s: 354 Ipc r/w Section 8 &amp; 12 of Pocso Act, 2012 P.S.: Ashok Vihar State V/s Sundar, S/o Shri Raghu Raj, R/o Village Kanapar, Ps Bas Gav, District Gorakhpur, Uttar Pradesh. Present Address: Wp­437, Wazirpur, Delhi. Date of institution of case: 07.08.2013 Date of arguments: 04.04.2015 Date of pronouncement of judgment: 23.04.2015 J U D G M E N T

**Mistake details:**
  - Token 19 'Court': FALSE POSITIVE (predicted=True, truth=False)  - Token 24 'Addl': FALSE NEGATIVE (predicted=False, truth=True)  - Token 25 '.': FALSE NEGATIVE (predicted=False, truth=True)  - Token 26 'Sessions': FALSE NEGATIVE (predicted=False, truth=True)  - Token 27 'Judge­01': FALSE NEGATIVE (predicted=False, truth=True)  - Token 28 ':': FALSE NEGATIVE (predicted=False, truth=True)  - Token 29 '(': FALSE NEGATIVE (predicted=False, truth=True)  - Token 30 'North­West': FALSE NEGATIVE (predicted=False, truth=True)  - Token 31 ')': FALSE NEGATIVE (predicted=False, truth=True)  - Token 32 ':': FALSE NEGATIVE (predicted=False, truth=True)  - Token 36 ':': FALSE NEGATIVE (predicted=False, truth=True)  - Token 37 'New': FALSE NEGATIVE (predicted=False, truth=True)  - Token 38 'Delhi': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 4 - Sample 16

**Text:** The Madras High Court has also adopted the same view, vide the decision In re, C. M. Raghavan where it was held that it is for the Magistrate to consider whether it as necessary to direct the personal attendance of the accused, who was exempted under Section 205, for questioning under Section 342 of the Code and that the omission to examine the accused personally does not vitiate the trial.

**Extracted targets:** ['Madras High Court', 'Magistrate']

**Text with predictions vs ground truth:**

The <span style="color: #00ff00; font-weight: bold;">Madras</span> <span style="color: #00ff00; font-weight: bold;">High</span> <span style="color: #00ff00; font-weight: bold;">Court</span> has also adopted the same view, vide the decision In re, C. M. Raghavan where it was held that it is for the <span style="color: #ff8800; font-weight: bold;">Magistrate</span> to consider whether it as necessary to direct the personal attendance of the accused, who was exempted under Section 205, for questioning under Section 342 of the Code and that the omission to examine the accused personally does not vitiate the trial.

**Mistake details:**
  - Token 30 'Magistrate': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 5 - Sample 20

**Text:** In The Court Of Shri P.S. Teji: District & Sessions Judge (East), Karkardooma Courts, Delhi Sc No.13/2011 Unique Case Id No.02402R0045182011 Fir No.150/2010 Police Station Crime Branch Under Section 186/353/307 Ipc & U/s 25/27/54/59 Arms Act State Versus Sandeep Chaudhary S/o Sh. Jayant Singh R/o Village Khairpur, Ps B.B. Nagar, District Bulandshahar, U.P. Date of Institution: 21.04.2011 Date of judgment reserved: 28.03.2014 Date of judgment: 11.04.2014 Judgment

**Extracted targets:** ['The Court Of Shri P.S. Teji', 'District & Sessions Judge (East), Karkardooma Courts, Delhi']

**Text with predictions vs ground truth:**

In <span style="color: #ff8800; font-weight: bold;">The</span> <span style="color: #ff8800; font-weight: bold;">Court</span> <span style="color: #ff8800; font-weight: bold;">Of</span> <span style="color: #ff8800; font-weight: bold;">Shri</span> <span style="color: #ff8800; font-weight: bold;">P.S</span> <span style="color: #ff8800; font-weight: bold;">.</span> <span style="color: #ff8800; font-weight: bold;">Teji</span>: <span style="color: #00ff00; font-weight: bold;">District</span> <span style="color: #00ff00; font-weight: bold;">&amp;</span> <span style="color: #00ff00; font-weight: bold;">Sessions</span> <span style="color: #00ff00; font-weight: bold;">Judge</span> <span style="color: #00ff00; font-weight: bold;">(</span> <span style="color: #00ff00; font-weight: bold;">East</span> <span style="color: #00ff00; font-weight: bold;">)</span> <span style="color: #00ff00; font-weight: bold;">,</span> <span style="color: #00ff00; font-weight: bold;">Karkardooma</span> <span style="color: #00ff00; font-weight: bold;">Courts</span> <span style="color: #00ff00; font-weight: bold;">,</span> <span style="color: #00ff00; font-weight: bold;">Delhi</span> Sc No.13/2011 Unique Case Id No.02402R0045182011 Fir No.150/2010 Police Station Crime Branch Under Section 186/353/307 Ipc &amp; U/s 25/27/54/59 Arms Act State Versus Sandeep Chaudhary S/o Sh. Jayant Singh R/o Village Khairpur, Ps B.B. Nagar, District Bulandshahar, U.P. Date of Institution: 21.04.2011 Date of judgment reserved: 28.03.2014 Date of judgment: 11.04.2014 Judgment

**Mistake details:**
  - Token 2 'The': FALSE POSITIVE (predicted=True, truth=False)  - Token 3 'Court': FALSE POSITIVE (predicted=True, truth=False)  - Token 4 'Of': FALSE POSITIVE (predicted=True, truth=False)  - Token 5 'Shri': FALSE POSITIVE (predicted=True, truth=False)  - Token 6 'P.S': FALSE POSITIVE (predicted=True, truth=False)  - Token 7 '.': FALSE POSITIVE (predicted=True, truth=False)  - Token 8 'Teji': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 6 - Sample 21

**Text:** Instead of referring to the other Decisions on which reliance was placed by the learned Counsel for the defendant we may refer to the decision in Lakshmi Narayan's case because it refers to the earlier decisions of the Supreme Court and also of the Federal Court.

**Extracted targets:** ['Supreme Court', 'Federal Court']

**Text with predictions vs ground truth:**

Instead of referring to the other Decisions on which reliance was placed by the learned Counsel for the defendant we may refer to the decision in Lakshmi Narayan &#x27;s case because it refers to the earlier decisions of the <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> and also of the <span style="color: #ff8800; font-weight: bold;">Federal</span> <span style="color: #ff8800; font-weight: bold;">Court</span>.

**Mistake details:**
  - Token 46 'Federal': FALSE POSITIVE (predicted=True, truth=False)  - Token 47 'Court': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 7 - Sample 24

**Text:** In The High Court Of Judicature For Raj.At Jaipur Bench, Jaipur. S.B. Civil Writ Petition No. 1928/2011 M/S Vikas Book Ltd. -- -Petitioner Vs. (1) Bank Of Baroda, Nehru Place, Tonk Road, Jaipur Through Its Authorized Officer Cum Manager (2) Shri Umraomal Chordia -- - Respondents With S.B.Civil Writ Petition No.2234/2011 (1) M/S. Arham Jewellers (2) Arpit Samcheti -- -Petitioners Vs. (1) Addl.Civil Judge (J.D.) Jaipur City, Jaipur. (2) A.D.J.No. 9, Jaipur City, Jaipur (3) Bank Of Baroda, Nehru Place, Tonk Road, Jaipur Through Its Manager (4) Sh.Umraomal Chordia -- -Respspondents. With S.B.Civil Writ Petition No. 2225/2011 M/S.Chordia Safe Deposit & Vaults Pvt.Ltd. -- -Petitioner Vs. (1) Addl.Civil Judge (J.D.) Jaipur City, Jaipur. (2) Addl.District Judge No. 9, Jaipur City, Jaipur. (3) Bank Of Baroda, Nehru Place, Tonk Road, Jaipur Through Its Manager, (4) Shri Shanti Kumar Vipul Kumar Chordia -- -Respondents Date Of Judgment

**Extracted targets:** ['High Court Of Judicature For Raj.At Jaipur Bench, Jaipur', 'Addl.Civil Judge (J.D.) Jaipur City, Jaipur', 'A.D.J.No. 9, Jaipur City, Jaipur', 'Addl.Civil Judge (J.D.) Jaipur City, Jaipur', 'Addl.District Judge No. 9, Jaipur City, Jaipur']

**Text with predictions vs ground truth:**

In The <span style="color: #00ff00; font-weight: bold;">High</span> <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #00ff00; font-weight: bold;">Of</span> <span style="color: #00ff00; font-weight: bold;">Judicature</span> <span style="color: #00ff00; font-weight: bold;">For</span> <span style="color: #00ff00; font-weight: bold;">Raj.At</span> <span style="color: #00ff00; font-weight: bold;">Jaipur</span> <span style="color: #00ff00; font-weight: bold;">Bench</span> <span style="color: #00ff00; font-weight: bold;">,</span> <span style="color: #00ff00; font-weight: bold;">Jaipur</span>. S.B. Civil Writ Petition No. 1928/2011 M/S Vikas Book Ltd. -- -Petitioner Vs. (1) Bank Of Baroda, Nehru Place, Tonk Road, Jaipur Through Its Authorized Officer Cum Manager (2) Shri Umraomal Chordia -- - Respondents With S.B.Civil Writ Petition No.2234/2011 (1) M/S. Arham Jewellers (2) Arpit Samcheti -- -Petitioners Vs. (1) <span style="color: #ff8800; font-weight: bold;">Addl.Civil</span> <span style="color: #ff8800; font-weight: bold;">Judge</span> <span style="color: #ff8800; font-weight: bold;">(</span> <span style="color: #ff8800; font-weight: bold;">J.D</span> <span style="color: #ff8800; font-weight: bold;">.</span> <span style="color: #ff8800; font-weight: bold;">)</span> <span style="color: #ff8800; font-weight: bold;">Jaipur</span> <span style="color: #ff8800; font-weight: bold;">City</span> <span style="color: #ff8800; font-weight: bold;">,</span> <span style="color: #ff8800; font-weight: bold;">Jaipur</span>. (2) <span style="color: #ff8800; font-weight: bold;">A.D.J.No</span> <span style="color: #ff8800; font-weight: bold;">.</span> <span style="color: #ff8800; font-weight: bold;">9</span> <span style="color: #ff8800; font-weight: bold;">,</span> <span style="color: #ff8800; font-weight: bold;">Jaipur</span> <span style="color: #ff8800; font-weight: bold;">City</span> <span style="color: #ff8800; font-weight: bold;">,</span> <span style="color: #ff8800; font-weight: bold;">Jaipur</span> (3) Bank Of Baroda, Nehru Place, Tonk Road, Jaipur Through Its Manager (4) Sh.Umraomal Chordia -- -Respspondents. With S.B.Civil Writ Petition No. 2225/2011 M/S.Chordia Safe Deposit &amp; Vaults Pvt.Ltd. -- -Petitioner Vs. (1) <span style="color: #ff0000; font-weight: bold;">Addl.Civil</span> <span style="color: #ff0000; font-weight: bold;">Judge</span> <span style="color: #ff0000; font-weight: bold;">(</span> <span style="color: #ff0000; font-weight: bold;">J.D</span> <span style="color: #ff0000; font-weight: bold;">.</span> <span style="color: #ff0000; font-weight: bold;">)</span> <span style="color: #ff0000; font-weight: bold;">Jaipur</span> <span style="color: #ff0000; font-weight: bold;">City</span> <span style="color: #ff0000; font-weight: bold;">,</span> <span style="color: #ff0000; font-weight: bold;">Jaipur</span>. (2) <span style="color: #00ff00; font-weight: bold;">Addl.District</span> <span style="color: #00ff00; font-weight: bold;">Judge</span> <span style="color: #00ff00; font-weight: bold;">No</span> <span style="color: #00ff00; font-weight: bold;">.</span> <span style="color: #00ff00; font-weight: bold;">9</span> <span style="color: #00ff00; font-weight: bold;">,</span> <span style="color: #00ff00; font-weight: bold;">Jaipur</span> <span style="color: #00ff00; font-weight: bold;">City</span> <span style="color: #00ff00; font-weight: bold;">,</span> <span style="color: #00ff00; font-weight: bold;">Jaipur</span>. (3) Bank Of Baroda, Nehru Place, Tonk Road, Jaipur Through Its Manager, (4) Shri Shanti Kumar Vipul Kumar Chordia -- -Respondents Date Of Judgment

**Mistake details:**
  - Token 81 'Addl.Civil': FALSE POSITIVE (predicted=True, truth=False)  - Token 82 'Judge': FALSE POSITIVE (predicted=True, truth=False)  - Token 83 '(': FALSE POSITIVE (predicted=True, truth=False)  - Token 84 'J.D': FALSE POSITIVE (predicted=True, truth=False)  - Token 85 '.': FALSE POSITIVE (predicted=True, truth=False)  - Token 86 ')': FALSE POSITIVE (predicted=True, truth=False)  - Token 87 'Jaipur': FALSE POSITIVE (predicted=True, truth=False)  - Token 88 'City': FALSE POSITIVE (predicted=True, truth=False)  - Token 89 ',': FALSE POSITIVE (predicted=True, truth=False)  - Token 90 'Jaipur': FALSE POSITIVE (predicted=True, truth=False)  - Token 95 'A.D.J.No': FALSE POSITIVE (predicted=True, truth=False)  - Token 96 '.': FALSE POSITIVE (predicted=True, truth=False)  - Token 97 '9': FALSE POSITIVE (predicted=True, truth=False)  - Token 98 ',': FALSE POSITIVE (predicted=True, truth=False)  - Token 99 'Jaipur': FALSE POSITIVE (predicted=True, truth=False)  - Token 100 'City': FALSE POSITIVE (predicted=True, truth=False)  - Token 101 ',': FALSE POSITIVE (predicted=True, truth=False)  - Token 102 'Jaipur': FALSE POSITIVE (predicted=True, truth=False)  - Token 148 'Addl.Civil': FALSE NEGATIVE (predicted=False, truth=True)  - Token 149 'Judge': FALSE NEGATIVE (predicted=False, truth=True)  - Token 150 '(': FALSE NEGATIVE (predicted=False, truth=True)  - Token 151 'J.D': FALSE NEGATIVE (predicted=False, truth=True)  - Token 152 '.': FALSE NEGATIVE (predicted=False, truth=True)  - Token 153 ')': FALSE NEGATIVE (predicted=False, truth=True)  - Token 154 'Jaipur': FALSE NEGATIVE (predicted=False, truth=True)  - Token 155 'City': FALSE NEGATIVE (predicted=False, truth=True)  - Token 156 ',': FALSE NEGATIVE (predicted=False, truth=True)  - Token 157 'Jaipur': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 8 - Sample 27

**Text:** That order was, however, set aside in revision by the Punjab. High Court which directed the trial court to allow the defendant to amend Iris written statement and to produce his father's alleged will.

**Extracted targets:** ['Punjab High Court', 'trial court']

**Text with predictions vs ground truth:**

That order was, however, set aside in revision by the <span style="color: #ff0000; font-weight: bold;">Punjab</span> <span style="color: #ff0000; font-weight: bold;">.</span> <span style="color: #ff0000; font-weight: bold;">High</span> <span style="color: #ff0000; font-weight: bold;">Court</span> which directed the <span style="color: #ff8800; font-weight: bold;">trial</span> <span style="color: #ff8800; font-weight: bold;">court</span> to allow the defendant to amend Iris written statement and to produce his father &#x27;s alleged will.

**Mistake details:**
  - Token 13 'Punjab': FALSE NEGATIVE (predicted=False, truth=True)  - Token 14 '.': FALSE NEGATIVE (predicted=False, truth=True)  - Token 15 'High': FALSE NEGATIVE (predicted=False, truth=True)  - Token 16 'Court': FALSE NEGATIVE (predicted=False, truth=True)  - Token 20 'trial': FALSE POSITIVE (predicted=True, truth=False)  - Token 21 'court': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 9 - Sample 37

**Text:** Thereafter, the Supreme Court in the case of R. Raghuram, supra, noticed the judgment of the Supreme Court in M/s.

**Extracted targets:** ['Supreme Court', 'Supreme Court']

**Text with predictions vs ground truth:**

Thereafter, the <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> in the case of R. Raghuram, supra, noticed the judgment of the <span style="color: #ff0000; font-weight: bold;">Supreme</span> <span style="color: #ff0000; font-weight: bold;">Court</span> in M/s.

**Mistake details:**
  - Token 20 'Supreme': FALSE NEGATIVE (predicted=False, truth=True)  - Token 21 'Court': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 10 - Sample 40

**Text:** 1 In The Court Of Sh. P.S.Teji: Addl. Sessions Judge: New Delhi. Sc No. 58/06 Fir No. 146/06 Ps: Badarpur. U/S. 364-A/34 Ipc. State Versus 1. Udhal Singh s/o Sh. Toonia R/o Village Lal Gadhi Ps Sikandarao, District Hathrash, Up. 2. Vinod @ Sahib Singh s/o Sh. Banwari Lal R/o Gali No.8, Dipawali Enclave, behind Molarband School, Faridabad, Haryana. Judgment

**Extracted targets:** ['Court']

**Text with predictions vs ground truth:**

1 In The <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #ff0000; font-weight: bold;">Of</span> <span style="color: #ff0000; font-weight: bold;">Sh</span> <span style="color: #ff0000; font-weight: bold;">.</span> <span style="color: #ff0000; font-weight: bold;">P.S.Teji</span> <span style="color: #ff0000; font-weight: bold;">:</span> <span style="color: #ff0000; font-weight: bold;">Addl</span> <span style="color: #ff0000; font-weight: bold;">.</span> <span style="color: #ff0000; font-weight: bold;">Sessions</span> <span style="color: #ff0000; font-weight: bold;">Judge</span> <span style="color: #ff0000; font-weight: bold;">:</span> <span style="color: #ff0000; font-weight: bold;">New</span> <span style="color: #ff0000; font-weight: bold;">Delhi</span>. Sc No. 58/06 Fir No. 146/06 Ps: Badarpur. U/S. 364-A/34 Ipc. State Versus 1. Udhal Singh s/o Sh. Toonia R/o Village Lal Gadhi Ps Sikandarao, District Hathrash, Up. 2. Vinod @ Sahib Singh s/o Sh. Banwari Lal R/o Gali No.8, Dipawali Enclave, behind Molarband School, Faridabad, Haryana. Judgment

**Mistake details:**
  - Token 5 'Of': FALSE NEGATIVE (predicted=False, truth=True)  - Token 6 'Sh': FALSE NEGATIVE (predicted=False, truth=True)  - Token 7 '.': FALSE NEGATIVE (predicted=False, truth=True)  - Token 8 'P.S.Teji': FALSE NEGATIVE (predicted=False, truth=True)  - Token 9 ':': FALSE NEGATIVE (predicted=False, truth=True)  - Token 10 'Addl': FALSE NEGATIVE (predicted=False, truth=True)  - Token 11 '.': FALSE NEGATIVE (predicted=False, truth=True)  - Token 12 'Sessions': FALSE NEGATIVE (predicted=False, truth=True)  - Token 13 'Judge': FALSE NEGATIVE (predicted=False, truth=True)  - Token 14 ':': FALSE NEGATIVE (predicted=False, truth=True)  - Token 15 'New': FALSE NEGATIVE (predicted=False, truth=True)  - Token 16 'Delhi': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 11 - Sample 50

**Text:** Now, in the light of the law laid down by the Apex Court, we have to examine whether the learned trial court has rightly recorded the finding of guilt as against appellant Surajbhan and that the circumstantial evidence relied upon by the prosecution unmistakably point to the only conclusion that accused appellant Surajbhan along with two others (since deceased) and none other is the perpetrator of the crime.

**Extracted targets:** ['Apex Court', 'court']

**Text with predictions vs ground truth:**

Now, in the light of the law laid down by the <span style="color: #00ff00; font-weight: bold;">Apex</span> <span style="color: #00ff00; font-weight: bold;">Court</span>, we have to examine whether the learned trial <span style="color: #ff8800; font-weight: bold;">court</span> has rightly recorded the finding of guilt as against appellant Surajbhan and that the circumstantial evidence relied upon by the prosecution unmistakably point to the only conclusion that accused appellant Surajbhan along with two others (since deceased) and none other is the perpetrator of the crime.

**Mistake details:**
  - Token 24 'court': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 12 - Sample 56

**Text:** In The High Court Of Uttarakhand At Nainital Writ Petition No. 1790 of 2006 (M/S) Chaman Lal S/o Prasadi Lal...... Petitioner Versus District Judge, Haridwar and others...... Respondents. Present: Mr. Siddhartha Singh, Advocate for the petitioner. Mr. Pankaj Purohit, Deputy Advocate General for the State of Uttarakhand. Mr. Rajendra Dobhal, Senior Advocate assisted by Lokendra Dobhal and Mr. Ashok Joshi, Advocates for the private respondents. Dated: 20th July, 2017 Judgment

**Extracted targets:** ['High Court Of Uttarakhand', 'District Judge, Haridwar']

**Text with predictions vs ground truth:**

In The <span style="color: #00ff00; font-weight: bold;">High</span> <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #00ff00; font-weight: bold;">Of</span> <span style="color: #00ff00; font-weight: bold;">Uttarakhand</span> <span style="color: #ff0000; font-weight: bold;">At</span> <span style="color: #ff0000; font-weight: bold;">Nainital</span> Writ Petition No. 1790 of 2006 (M/S) Chaman Lal S/o Prasadi Lal...... Petitioner Versus <span style="color: #ff8800; font-weight: bold;">District</span> <span style="color: #ff8800; font-weight: bold;">Judge</span> <span style="color: #ff8800; font-weight: bold;">,</span> <span style="color: #ff8800; font-weight: bold;">Haridwar</span> and others...... Respondents. Present: Mr. Siddhartha Singh, Advocate for the petitioner. Mr. Pankaj Purohit, Deputy Advocate General for the State of Uttarakhand. Mr. Rajendra Dobhal, Senior Advocate assisted by Lokendra Dobhal and Mr. Ashok Joshi, Advocates for the private respondents. Dated: 20th July, 2017 Judgment

**Mistake details:**
  - Token 7 'At': FALSE NEGATIVE (predicted=False, truth=True)  - Token 8 'Nainital': FALSE NEGATIVE (predicted=False, truth=True)  - Token 27 'District': FALSE POSITIVE (predicted=True, truth=False)  - Token 28 'Judge': FALSE POSITIVE (predicted=True, truth=False)  - Token 29 ',': FALSE POSITIVE (predicted=True, truth=False)  - Token 30 'Haridwar': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 13 - Sample 58

**Text:** IN THE HIGH COURT OF DELHI AT NEW DELHI Reserved on: 24th March, 2014

**Extracted targets:** ['HIGH COURT OF DELHI']

**Text with predictions vs ground truth:**

IN THE <span style="color: #00ff00; font-weight: bold;">HIGH</span> <span style="color: #00ff00; font-weight: bold;">COURT</span> <span style="color: #00ff00; font-weight: bold;">OF</span> <span style="color: #00ff00; font-weight: bold;">DELHI</span> <span style="color: #ff0000; font-weight: bold;">AT</span> <span style="color: #ff0000; font-weight: bold;">NEW</span> <span style="color: #ff0000; font-weight: bold;">DELHI</span> Reserved on: 24th March, 2014

**Mistake details:**
  - Token 7 'AT': FALSE NEGATIVE (predicted=False, truth=True)  - Token 8 'NEW': FALSE NEGATIVE (predicted=False, truth=True)  - Token 9 'DELHI': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 14 - Sample 59

**Text:** Petitioner: The United Commercial Bank Ltd., Calcutta Vs. Respondent: The Commissioner Of Income-Tax, West Bengal Date Of Judgment

**Extracted targets:** ['Commissioner Of Income-Tax, West Bengal']

**Text with predictions vs ground truth:**

Petitioner: The United Commercial Bank Ltd., Calcutta Vs. Respondent: The <span style="color: #ff8800; font-weight: bold;">Commissioner</span> <span style="color: #ff8800; font-weight: bold;">Of</span> <span style="color: #ff8800; font-weight: bold;">Income-Tax</span> <span style="color: #ff8800; font-weight: bold;">,</span> <span style="color: #ff8800; font-weight: bold;">West</span> <span style="color: #ff8800; font-weight: bold;">Bengal</span> Date Of Judgment

**Mistake details:**
  - Token 14 'Commissioner': FALSE POSITIVE (predicted=True, truth=False)  - Token 15 'Of': FALSE POSITIVE (predicted=True, truth=False)  - Token 16 'Income-Tax': FALSE POSITIVE (predicted=True, truth=False)  - Token 17 ',': FALSE POSITIVE (predicted=True, truth=False)  - Token 18 'West': FALSE POSITIVE (predicted=True, truth=False)  - Token 19 'Bengal': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 15 - Sample 61

**Text:** In The Court Of Shri Manoj Kumar: Additional Sessions Judge­4 (South District), New Delhi Criminal Appeal No. 01/14 (Original no. 58/13) Unique Id No.: 02406R0035022013 In the matter of: Nitin Chaudhary, S/o Sh. Ved Chaudhary, R/o G­93, Lgf, Saket, New Delhi­110017................. Appellant Versus Amit Khaneja, S/o Sh. Ashok Khaneja, R/o A­12/4, Rana Pratap Bagh, Delhi­110007............. Respondent Date of Institution: 08.02.2013 Date of Reserving judgment: 29.5.2014 Date of pronouncement: 31.5.2014 For Appellant: Mr. Khalil A. Ansari, Advocate. Criminal Appeal No. 01/14 Page no. 1 of 28 For Respondent: Mr. R. P. Sharma, Advocate. Judgment

**Extracted targets:** ['Court Of Shri Manoj Kumar']

**Text with predictions vs ground truth:**

In The <span style="color: #ff8800; font-weight: bold;">Court</span> <span style="color: #ff8800; font-weight: bold;">Of</span> <span style="color: #ff8800; font-weight: bold;">Shri</span> <span style="color: #ff8800; font-weight: bold;">Manoj</span> <span style="color: #ff8800; font-weight: bold;">Kumar</span>: <span style="color: #ff0000; font-weight: bold;">Additional</span> <span style="color: #ff0000; font-weight: bold;">Sessions</span> <span style="color: #ff0000; font-weight: bold;">Judge­4</span> <span style="color: #ff0000; font-weight: bold;">(</span> <span style="color: #ff0000; font-weight: bold;">South</span> <span style="color: #ff0000; font-weight: bold;">District</span> <span style="color: #ff0000; font-weight: bold;">)</span> <span style="color: #ff0000; font-weight: bold;">,</span> <span style="color: #ff0000; font-weight: bold;">New</span> <span style="color: #ff0000; font-weight: bold;">Delhi</span> Criminal Appeal No. 01/14 (Original no. 58/13) Unique Id No.: 02406R0035022013 In the matter of: Nitin Chaudhary, S/o Sh. Ved Chaudhary, R/o G­93, Lgf, Saket, New Delhi­110017................. Appellant Versus Amit Khaneja, S/o Sh. Ashok Khaneja, R/o A­12/4, Rana Pratap Bagh, Delhi­110007............. Respondent Date of Institution: 08.02.2013 Date of Reserving judgment: 29.5.2014 Date of pronouncement: 31.5.2014 For Appellant: Mr. Khalil A. Ansari, Advocate. Criminal Appeal No. 01/14 Page no. 1 of 28 For Respondent: Mr. R. P. Sharma, Advocate. Judgment

**Mistake details:**
  - Token 3 'Court': FALSE POSITIVE (predicted=True, truth=False)  - Token 4 'Of': FALSE POSITIVE (predicted=True, truth=False)  - Token 5 'Shri': FALSE POSITIVE (predicted=True, truth=False)  - Token 6 'Manoj': FALSE POSITIVE (predicted=True, truth=False)  - Token 7 'Kumar': FALSE POSITIVE (predicted=True, truth=False)  - Token 9 'Additional': FALSE NEGATIVE (predicted=False, truth=True)  - Token 10 'Sessions': FALSE NEGATIVE (predicted=False, truth=True)  - Token 11 'Judge­4': FALSE NEGATIVE (predicted=False, truth=True)  - Token 12 '(': FALSE NEGATIVE (predicted=False, truth=True)  - Token 13 'South': FALSE NEGATIVE (predicted=False, truth=True)  - Token 14 'District': FALSE NEGATIVE (predicted=False, truth=True)  - Token 15 ')': FALSE NEGATIVE (predicted=False, truth=True)  - Token 16 ',': FALSE NEGATIVE (predicted=False, truth=True)  - Token 17 'New': FALSE NEGATIVE (predicted=False, truth=True)  - Token 18 'Delhi': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 16 - Sample 63

**Text:** After extracting Section 195 (1) (b) (ii) of the Code, the Supreme Court observed that``there could not be any dispute that if forgery was committed while the document was in the custody of a Court, then the prosecution could be launched only with a complaint made by that Court.

**Extracted targets:** ['Supreme Court', '', '.']

**Text with predictions vs ground truth:**

After extracting Section 195 (1) (b) (ii) of the Code, the <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> observed that``there could not be any dispute that if forgery was committed while the document was in the custody of a Court, then the prosecution could be launched only with a complaint made by that Court <span style="color: #ff8800; font-weight: bold;">.</span>

**Mistake details:**
  - Token 60 '.': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 17 - Sample 67

**Text:** As the section was silent about the grounds on which the permission to file a suit for eviction could be granted to the landlord the Supreme Court found as a necessary corollary to the quasi-judicial power``that the District Magistrate has to weigh the pros and cons of the matter and come to a certain conclusion he made the order.

**Extracted targets:** ['Supreme Court', 'District Magistrate']

**Text with predictions vs ground truth:**

As the section was silent about the grounds on which the permission to file a suit for eviction could be granted to the landlord the <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> found as a necessary corollary to the quasi-judicial power``that the <span style="color: #ff8800; font-weight: bold;">District</span> <span style="color: #ff8800; font-weight: bold;">Magistrate</span> has to weigh the pros and cons of the matter and come to a certain conclusion he made the order.

**Mistake details:**
  - Token 40 'District': FALSE POSITIVE (predicted=True, truth=False)  - Token 41 'Magistrate': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 18 - Sample 70

**Text:** S.B.Civil First Appeal No. 16/1986-Madan Singh vs. Suraj Kanwar- S.B.Civil First Appeal No. 478/2006-Madan Singh vs. Rajendra Singh & Ors. Judgment dt:11/8/2011 1/32 In The High Court Of Judicature For Rajasthan At Jodhpur Judgment

**Extracted targets:** ['High Court']

**Text with predictions vs ground truth:**

S.B.Civil First Appeal No. 16/1986-Madan Singh vs. Suraj Kanwar- S.B.Civil First Appeal No. 478/2006-Madan Singh vs. Rajendra Singh &amp; Ors. Judgment dt:11/8/2011 1/32 In The <span style="color: #00ff00; font-weight: bold;">High</span> <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #ff0000; font-weight: bold;">Of</span> <span style="color: #ff0000; font-weight: bold;">Judicature</span> <span style="color: #ff0000; font-weight: bold;">For</span> <span style="color: #ff0000; font-weight: bold;">Rajasthan</span> <span style="color: #ff0000; font-weight: bold;">At</span> <span style="color: #ff0000; font-weight: bold;">Jodhpur</span> Judgment

**Mistake details:**
  - Token 31 'Of': FALSE NEGATIVE (predicted=False, truth=True)  - Token 32 'Judicature': FALSE NEGATIVE (predicted=False, truth=True)  - Token 33 'For': FALSE NEGATIVE (predicted=False, truth=True)  - Token 34 'Rajasthan': FALSE NEGATIVE (predicted=False, truth=True)  - Token 35 'At': FALSE NEGATIVE (predicted=False, truth=True)  - Token 36 'Jodhpur': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 19 - Sample 75

**Text:** The two leading decisions are 8 Beng LR 433, a decision of this Court given in 1872 and ILR 35 Mad 1, a decision of the Madras High Court, given in 1910.

**Extracted targets:** ['Court', 'Madras High Court']

**Text with predictions vs ground truth:**

The two leading decisions are 8 Beng LR 433, a decision of this <span style="color: #ff8800; font-weight: bold;">Court</span> given in 1872 and ILR 35 Mad 1, a decision of the <span style="color: #00ff00; font-weight: bold;">Madras</span> <span style="color: #00ff00; font-weight: bold;">High</span> <span style="color: #00ff00; font-weight: bold;">Court</span>, given in 1910.

**Mistake details:**
  - Token 15 'Court': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 20 - Sample 76

**Text:** Law laid down by the Supreme Court: - 18.

**Extracted targets:** ['Supreme Court']

**Text with predictions vs ground truth:**

Law laid down by the <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #ff0000; font-weight: bold;">:</span> <span style="color: #ff0000; font-weight: bold;">-</span> 18.

**Mistake details:**
  - Token 8 ':': FALSE NEGATIVE (predicted=False, truth=True)  - Token 9 '-': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 21 - Sample 79

**Text:** Under these circumstances, as per Section 3 of the Act, driver of the tanker lorry was having valid and effective driving licence, despite of that, the Tribunal has committed an error in fastening the liability on the owner of tanker lorry.

**Extracted targets:** ['Tribunal']

**Text with predictions vs ground truth:**

Under these circumstances, as per Section 3 of the Act, driver of the tanker lorry was having valid and effective driving licence, despite of that, the <span style="color: #ff8800; font-weight: bold;">Tribunal</span> has committed an error in fastening the liability on the owner of tanker lorry.

**Mistake details:**
  - Token 31 'Tribunal': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 22 - Sample 82

**Text:** In The Court Of Sh. Pitamber Dutt; Adj (Central) -11, Delhi Suit No. 927/08 Unique I.D No. 02401C0517582007 1. Rajan Rattan S/o Sh. Sanjay Rattan 2. Hunny Rattan S/o Sh. Sanjay Rattan 3. Usha Rattan W/o Sh. Sanjay Rattan All Residents of House No. A-1/78, Sector-4, Rohini, Delhi....... P l a i n t i f f s Versus 1. Sh. Kunti Nandan Sharma S/o late Sh. Chunni Lal R/o L-86-A, Malviya Nagar, New Delhi 2. Smt. Jyoti W/o Sh. Rajesh Sharma House no. 12, Biharipur, Krolan, Bareilly, U.P....... D e f e n d a n t s Date of Institution of Suit: 19.05.2007 Date when reserved for orders: 10.12.2013 Date of Decision: 18.12.2013 Judgment

**Extracted targets:** ['Court']

**Text with predictions vs ground truth:**

In The <span style="color: #00ff00; font-weight: bold;">Court</span> <span style="color: #ff0000; font-weight: bold;">Of</span> <span style="color: #ff0000; font-weight: bold;">Sh</span> <span style="color: #ff0000; font-weight: bold;">.</span> <span style="color: #ff0000; font-weight: bold;">Pitamber</span> <span style="color: #ff0000; font-weight: bold;">Dutt</span> <span style="color: #ff0000; font-weight: bold;">;</span> <span style="color: #ff0000; font-weight: bold;">Adj</span> <span style="color: #ff0000; font-weight: bold;">(</span> <span style="color: #ff0000; font-weight: bold;">Central</span> <span style="color: #ff0000; font-weight: bold;">)</span> <span style="color: #ff0000; font-weight: bold;">-11</span> <span style="color: #ff0000; font-weight: bold;">,</span> <span style="color: #ff0000; font-weight: bold;">Delhi</span> Suit No. 927/08 Unique I.D No. 02401C0517582007 1. Rajan Rattan S/o Sh. Sanjay Rattan 2. Hunny Rattan S/o Sh. Sanjay Rattan 3. Usha Rattan W/o Sh. Sanjay Rattan All Residents of House No. A-1/78, Sector-4, Rohini, Delhi....... P l a i n t i f f s Versus 1. Sh. Kunti Nandan Sharma S/o late Sh. Chunni Lal R/o L-86-A, Malviya Nagar, New Delhi 2. Smt. Jyoti W/o Sh. Rajesh Sharma House no. 12, Biharipur, Krolan, Bareilly, U.P....... D e f e n d a n t s Date of Institution of Suit: 19.05.2007 Date when reserved for orders: 10.12.2013 Date of Decision: 18.12.2013 Judgment

**Mistake details:**
  - Token 4 'Of': FALSE NEGATIVE (predicted=False, truth=True)  - Token 5 'Sh': FALSE NEGATIVE (predicted=False, truth=True)  - Token 6 '.': FALSE NEGATIVE (predicted=False, truth=True)  - Token 7 'Pitamber': FALSE NEGATIVE (predicted=False, truth=True)  - Token 8 'Dutt': FALSE NEGATIVE (predicted=False, truth=True)  - Token 9 ';': FALSE NEGATIVE (predicted=False, truth=True)  - Token 10 'Adj': FALSE NEGATIVE (predicted=False, truth=True)  - Token 11 '(': FALSE NEGATIVE (predicted=False, truth=True)  - Token 12 'Central': FALSE NEGATIVE (predicted=False, truth=True)  - Token 13 ')': FALSE NEGATIVE (predicted=False, truth=True)  - Token 14 '-11': FALSE NEGATIVE (predicted=False, truth=True)  - Token 15 ',': FALSE NEGATIVE (predicted=False, truth=True)  - Token 16 'Delhi': FALSE NEGATIVE (predicted=False, truth=True)

### Mistake 23 - Sample 87

**Text:** We are inclined to agree that the grant of a constitutional passport to the Supreme Court by the High Court is not a matter of easy insouciance but anxious advertence to the dual vital requirements built into Art. 133 (1) by specific amendment.

**Extracted targets:** ['Supreme Court', 'High Court']

**Text with predictions vs ground truth:**

We are inclined to agree that the grant of a constitutional passport to the <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> by the <span style="color: #ff8800; font-weight: bold;">High</span> <span style="color: #ff8800; font-weight: bold;">Court</span> is not a matter of easy insouciance but anxious advertence to the dual vital requirements built into Art. 133 (1) by specific amendment.

**Mistake details:**
  - Token 19 'High': FALSE POSITIVE (predicted=True, truth=False)  - Token 20 'Court': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 24 - Sample 89

**Text:** The Apex Court held that the trial Court, was right, in coming to the conclusion, that the accused were found in conscious possession of charas, as they had failed to explain, as to how they were travelling in a Car together, which was not a public vehicle.

**Extracted targets:** ['Apex Court', 'trial Court']

**Text with predictions vs ground truth:**

The <span style="color: #00ff00; font-weight: bold;">Apex</span> <span style="color: #00ff00; font-weight: bold;">Court</span> held that the <span style="color: #ff8800; font-weight: bold;">trial</span> <span style="color: #ff8800; font-weight: bold;">Court</span>, was right, in coming to the conclusion, that the accused were found in conscious possession of charas, as they had failed to explain, as to how they were travelling in a Car together, which was not a public vehicle.

**Mistake details:**
  - Token 7 'trial': FALSE POSITIVE (predicted=True, truth=False)  - Token 8 'Court': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 25 - Sample 92

**Text:** Counsel appearing for respondents 4 and 5 referred to the decisions of this Court and the Supreme court which the Tribunal has relied on while passing the award and contended that the word'legal heirs'include illegitimate children also.

**Extracted targets:** ['Court', 'Supreme Court', 'Tribunal']

**Text with predictions vs ground truth:**

Counsel appearing for respondents 4 and 5 referred to the decisions of this <span style="color: #ff8800; font-weight: bold;">Court</span> and the <span style="color: #ff0000; font-weight: bold;">Supreme</span> <span style="color: #ff0000; font-weight: bold;">court</span> which the <span style="color: #ff8800; font-weight: bold;">Tribunal</span> has relied on while passing the award and contended that the word &#x27;legal heirs &#x27; include illegitimate children also.

**Mistake details:**
  - Token 14 'Court': FALSE POSITIVE (predicted=True, truth=False)  - Token 17 'Supreme': FALSE NEGATIVE (predicted=False, truth=True)  - Token 18 'court': FALSE NEGATIVE (predicted=False, truth=True)  - Token 21 'Tribunal': FALSE POSITIVE (predicted=True, truth=False)

### Mistake 26 - Sample 99

**Text:** If the Supreme Court had declared that Section 20 as intra vires the matter would have come to an end so far as the High Courts are concerned.

**Extracted targets:** ['Supreme Court', 'High Courts']

**Text with predictions vs ground truth:**

If the <span style="color: #00ff00; font-weight: bold;">Supreme</span> <span style="color: #00ff00; font-weight: bold;">Court</span> had declared that Section 20 as intra vires the matter would have come to an end so far as the <span style="color: #ff8800; font-weight: bold;">High</span> <span style="color: #ff8800; font-weight: bold;">Courts</span> are concerned.

**Mistake details:**
  - Token 25 'High': FALSE POSITIVE (predicted=True, truth=False)  - Token 26 'Courts': FALSE POSITIVE (predicted=True, truth=False)