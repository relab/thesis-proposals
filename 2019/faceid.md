# Document Verification System on iOS with FaceID/TouchID

### Supervisor: Prof. Hein Meling 

### Prerequisites: 

- Excellent programming skills
- Desire to learn Swift/iOS programming
- Interest in learning about biometrics and security and iOS app development

### Background:

Managing secure information has become easier in recent years, with the introduction of fingerprint and face recognition on mobile devices. These devices secure the biometric template data, representing a user's fingerprint or facial features, in a secure enclave processor on the device that cannot be accessed directly, but the processor can be used to unlock access to protected data or the apps themselves.

### BBChain Background:

This thesis is given in the context of the BBChain research project.

One of the goals in the BBChain project, is the vision of a document verification system with globally distributed participants. A participant can be a signer, a verifier, or a document owner. A signer signs documents that can later be verified by a verifier. The document content can be published openly, or kept private between the main participants (the signer, document owner, and verifier). However, the signature of the document must be published openly to guarantee the trust relationships. The document owner should also be able to verify the document, but is otherwise considered untrusted. That is, the owner may use the document to prove that the content is correct and unmodified, but the owner may have an incentive to change the document’s content in his favor. 

### Project description: 

In this project the goal is to build an iOS app that can use the FaceID/TouchID features of the iOS platform to support the requirements outlined above. The project should use a degree certificate system (grade transcripts) as an example application, where document owners should be prevented from modifying their own degree certificates. Moreover, the document owner should be in control of who gains access to the document, for example other universities or places of employment where the document owner wishes to apply.

The system needs to be design under the constraints of iOS and on-device biometric features for unlocking access to cryptographic keys needed for encryption/decryption and signing documents. 

In a real-world application, we envision using a blockchain to prevent tampering and unauthorized deletion. However, in the prototype implementation, a simple database or a file-based storage server can be used for off-device storage of documents. 

### Tasks / Milestones: 

- Study basic biometrics and applied cryptography
- Study Swift/iOS programming, especially focused on FaceID/TouchID APIs
- Design the system given the constraint of iOS and on-device biometric features
- Model the design of the degree certificate system in UML (or similar)
- Implement a prototype system using off-device storage of documents
- Evaluate the performance and security of the system

