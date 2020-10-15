# Biometrics from ECG Signals on Apple Watch

### Supervisors: Prof. Hein Meling and Prof. Trygve Eftestøl

### Prerequisites:

- Knowledgable in pattern recognition and machine learning
- Excellent programming skills
- Desire to learn Swift/iOS programming for the Apple Watch
- Interest in learning about biometrics and security and iOS app development

The project may be scaled up to accommodate two students, one specialzing in the machine learning aspects, and the other specializing in iOS app development part.

### Background:

Biometrics as represented by fingerprints and face recognition have become popular on mobile devices in recent years, as a means to identify persons and authorize access to online resources, documents and even for payment. 

Existing biometric systems such as fingerprint and face recognition are based on external attributes of a human, and may be more susceptible to attacks. Moreover, with the increasing reliance on biometrics it is likely that some systems will seek to protect assets with multiple distinct biometric traits, also called a biometric fusion system. In this design space, we envision that certain assets can also be protected using ECG-based biometrics.

The most recent incarnation of the Apple Watch provides sensors for reading ECG signals of the wearer. ECG signals has previously been used as a biometric trait to identify a person; see links below.

### Project Description:

The goal in this project is to build a system for extracting biometric data (called a biometric template) from the ECG sensor on the Apple Watch. This biometric template can possibly be used for various tasks, such as unlocking the device and provide access to documents and other resources. As such it is important that such biometric templates are protected, which can be done using secure enclave technology on the Apple Watch.

However, to build a ECG-based biometric system, we need to sample/extract ECG sensor data from multiple persons using the Apple Watch sensor and provide this as input to a matching algorithm. This matching algorithm is to be developed as a machine learning model based on ECG samples collected from some population of people. The Apple Watch should have the necessary support for running such machine learning models using its on device neural engine.

An Apple Watch can be made available for testing purposes.

### Tasks / Milestones:

- Study the biometrics literature, especially related to ECG signals
- Develop tools for collecting ECG signal samples from the Apple Watch
- Design data collection scheme to capture varying ECG measurements of users
- Collect ECG samples from user population to be used in designing machine learning model
- Develop a machine learning model that can be executed on the Apple Watch
- Evaluate the machine learning model as a biometrics system for granting/denying access to users

### References:

- https://developer.apple.com/healthkit/
- https://ieeexplore.ieee.org/document/5634493
- https://www.sciencedirect.com/science/article/pii/S1566253516300446
- http://www.catalyst-inc.org/techwatch/bsecur
- https://www.wired.com/insights/2014/06/heartbeat-may-soon-password/
- https://www.economist.com/babbage/2013/05/09/a-heart-to-my-key
- https://www.smithsonianmag.com/innovation/using-your-heartbeat-password-180961952/
- https://www.alivecor.com

- https://file.scirp.org/pdf/JCC_2017122809211748.pdf
- http://paper.ijcsns.org/07_book/201012/20101220.pdf

