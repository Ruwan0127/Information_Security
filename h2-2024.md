# Treat Modeling Manifesto

- Threat modeling is analyzing representations of a system to highlight concerns about security and privacy characteristics.

- Used to recognize what is wrong in the system, and anyone should treat model.

- The Threat Modeling Manifesto follows a similar format to that of the Agile Manifesto by values and principles guidelines.


https://www.threatmodelingmanifesto.org/

<br>

# World's Shortest Threat Modeling Course - Adam Shostack

- Treat modeling is a set of methods that allow us to think about security and we need to build secure as we need, and it is inexpensive.

  ## What are we working on ?
- We need collaboration.
- We are sketching our ideass
- Add details and identify what can go wrong.
- Data flow digrams are heavily associated in treat modeling. It consists with five elements.
    - external entities - (not under our control)
    - processes  - (under our control)
    - connectors - ( shoe data flow)
    - drums to storedata
    - trust boundary
 
   ## What can go wrong ?

- We can ask what can go wrong and pay attention to the answers and identify the consistancy. 
- For that we can use "STRIDE"
  - Spoofing
  - Tampering
  - Repudiation
  - Information Disclosure
  - Denial Service
  - Elevation of Privilages
 
   ## What Are We Going To Do 

   - Track our work
   - Risk management
 
  The question, "would you recommend threat modeling to a colleague" is good way to identify that you have done a good job.

  

https://www.youtube.com/playlist?list=PLCVhBqLDKoOOZqKt74QI4pbDUnXSQo0nf


#  Threat Modeling Cheat Sheet

This explains the following points,
- Threat Modeling Overview
- Advantages of Threat Modeling
- Key Threat Modeling Phases

https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html



# Security hygiene. 

What basic security practices should everyone follow? 

- Installing antivirus and malware software
- Using firewalls to stop unauthorized access
- Updating software regularly
- Setting strong passwords
- Employing device encryption
- Backing up regularly
- Wiping hard drives.
- Avoid clicking on suspicious links, 

https://www.linkedin.com/pulse/cyber-hygiene-practices-individuals-businesses-prevent-attacks/
<br>

# Make-belief boogie-man - a threat model for imaginary company.

A long, extensive answer with narrative, analysis and a diagram is expected.
Create an imaginary company and create threat model.
Business requirements come from business, technical specialist help with tech. Inlude this in your narrative.
Your analysis should cover all parts of the four question model (four key questions in Threat modeling manifesto)

## What are we working on?

My tuition class, "Royal Academy" focuses on providing quality education to 30 students. We collect and store personal data, including addresses, phone numbers, and email addresses, for both students and their guardians. Also we manage monthly test grades and comments for individual students. The key assets in  are the personal data of students and their guardians, as well as the educational content, including notes and the question bank.


### Description:

- Student Database: Stores personal information (address, phone number, email,payment details) of each student and their guardian.
- Monthly Test Records: Database containing grades and comments for each student.
- Educational Content Repository: Contains notes, question bank, and other teaching materials.

### Key assets:

- Personal data, especially guardian information, is crucial for communication and emergencies.
- Educational content, including notes and the question bank, is valuable intellectual property.

 
## What can go wrong?

Threat Modeling Approach is STRIDE

The following risks have identified:
- Data Breach: Unauthorized access to the student database may result in the exposure of personal information, violating privacy.
- Data Corruption: Intentional or accidental changes to monthly test records may lead to incorrect grading and loss of trust.
- Insider Threats: Misuse of access by an employee or a student to exploit or manipulate personal data.
- Unavailability of Educational Content: Loss or corruption of educational materials could disrupt teaching and impact student learning.
- Phishing Attacks: Attempted to gain access to login details, potentially leading to unauthorized access to the database.

Prioritization of Risks:

High Value: 
Data breach cause the highest risk due to the sensitive nature of personal information.
- Insider Threats:
- Considering the small class size, insider threats are significant concerns.

Mitigation Strategies:
- Encryption of Personal Data: Ensure all personal data is stored and transmitted securely using encryption.
- Access Controls: Implement strict access controls to limit who can view and modify student records.
- Regular Backups: Conduct regular backups of educational content to prevent loss in case of corruption or accidental deletion.
- Employee Training: Educate staff and students on the importance of data security, recognizing and reporting phishing attempts.

## What are we going to do about it?

- Risk Mitigation Actions:

  - Data Encryption:
    To protect against unauthorized access, end-to-end encryption is implement for stored personal data.

  - Access Controls:
    Role-based access controls is enforced,which grant minimal permissions based on job responsibilities.

  - Regular Backups:
    Automated backup procedures are set up for educational content to ensure quick recovery in case of data loss.

  - Employee Training:
    Periodic training sessions are conducting to educate staff and students about recognizing and reporting security threats.


## Did we do a good enough job?

To evaluate the success of put in place security measures, conduct regular security audits.

- Mechanism of Feedback:
Provide a way for parents and students to voice concerns about privacy and data security.

- Updates to Policies:
Review and update data security policies on a regular basis to reflect new risks and regulatory changes.
The plan for responding to incidents.

To guarantee a prompt and efficient reaction to any security issue, create and test an incident response plan on a regular basis.


Resources,

1. https://docs.microsoft.com/en-us/azure/architecture/ threat-model/stride-threat-model
2. https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html
3. https://www.youtube.com/playlist?list=PLCVhBqLDKoOOZqKt74QI4pbDUnXSQo0nf
4. https://www.threatmodelingmanifesto.org/





