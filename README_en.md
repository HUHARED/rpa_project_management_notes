目录

- [1. Proface](#1-proface)
- [2. Basic Concepts](#2-basic-concepts)
  - [2.1. The Typical Duration of RPA Projects](#21-the-typical-duration-of-rpa-projects)
  - [2.2. Explanation of Terms](#22-explanation-of-terms)
- [3. Requirements Change Control (Demand Management)](#3-requirements-change-control-demand-management)
- [4. Risk Management (to be translated)](#4-risk-management-to-be-translated)
  - [4.1. Risk Identification (to be translated)](#41-risk-identification-to-be-translated)
  - [4.2. Risk Follow-up (to be translated)](#42-risk-follow-up-to-be-translated)
  - [4.3. Overview of Common Risks (to be updated)](#43-overview-of-common-risks-to-be-updated)
- [5. Stakeholder Management (to be updated)](#5-stakeholder-management-to-be-updated)
- [6. Program Design (to be updated)](#6-program-design-to-be-updated)
- [7. License](#7-license)

# 1. Proface

Hi, these are my notes on RPA project management. They are designed to summarize and share my management experiences, while also incorporating a bit of technical expertise.

So far, I have used UiBot, Encoo, and UiPath. The applicability of my notes may vary due to differences in RPA software, so I will try to highlight any software-specific situations.

I've been responsible for develping small and medium-sized project at a small party B company. These management experiences are a reflection and summary of my studies and project, so it could not be applicable to all situations, and some opinions might be biased, please forgive me for that. I guess the notes will be more useful for RPA practitioners working in small to medium-sized companies. The scenarios discussed in the notes are primarily from the perspective of a party B engineer. (Hence, in the notes, generally "we" generally refers to the "party B" and "the other party" refers to the "party A")

If you have any questions or opinions, feel free to leave a comment on the platforms where the notes are published. I'll do my best to provide constructive responses.

My targets:

* To document and share the insights gained from my work and studies, ultimately supporting my own career growth.
* To help RPA practitioners (especially junior engineers ) avoid common piffalls. (I'll provide explainations in brackets for terms that may be unfamiliar to junior engineers. Additionally, I might over-explain at times to ensure clarity for readers, and I apologize in advance for that.)
  * In my view, management is a form of technology, a pure technical engineer can benefit from learning from some management knowledge. This can improve communication, efficiency, teamwork, decision-making, ultimately leading to a more enjoyable project experience.
* To practice my English writing skills.

The RPA business is still expanding rapidly, if the notes could make a small impact in the field, and help some engineers along the way, that would be a wonderful achievement. (if, however, most RPA positions are replaced by general AI before that happens, I just wish us good luck.)

The notes are published on the following platforms:

* GitHub (Chinese):
* UiBot forum:
* GitHub (English):
* UiPath forum:

Before exhausting the management knowledge I think is worth sharing, I plan to update the notes at least twice a month, with a total word count of over 20,000 words.

The notes will primarily be updated on GitHub, and then synchronized to other platforms at a convenient time.

Fell free to leave comments on the privously mentioned platforms. Thank you.

If you're interested in UiBot skills, you can check out my UiBot notes: [【笔记分享】个人UiBot使用经验、笔记、技巧分享](https://forum.uibot.com.cn/thread-12458.htm)

# 2. Basic Concepts

To help RPA engineers who never studied management understand the following content, let's first go over some basic concepts.

Dui to the limitations of my experiences, the explanations of these basic concepts might differ slightly from those provided by professionals.

## 2.1. The Typical Duration of RPA Projects

1. Before a project started

   1. Before the project manager learns about the project, the sales and marketing team have already completed the research and comunicated with the potential client.
2. Start the project

   1. The Project Manger, Business Analyst, Program Designer, Implementation Engineer, Client, and others will analyze and define the scope of the task (what needs to be done and how the result should be), determine the required resources (such as human resources, software, hardware), identify potential risks, determine how much to pay (common options are a fixed payment or payment based on man-days), and discuss other project-related details using tools like emails, instant messaging software, and video conferencing software.
3. Business Analysis and Program Design

   1. We will analyze the business that are to to be automated, create workflow diagrams, and develop both high-level and detailed program designs.
4. Implementation and Testing

   1. The Implementation Engineer develops the program based on the program design documents. From my understanding, the Implementation Engineer is typically responsible for conducting testing (including Unit Testing and Integration Testing) as well.
5. Deployment and System Testing

   1. After the RPA program had passed Integration Testing in the development environment, it needs to be deployed in the product environment, which typically involves installing the RPA software, browser, and Excel.
   2. Once the deployment is complete, we need to test the program in the product environment, also known as System Testing.
6. Customer Training and Product Acceptance

   1. If the System Testing is completed, depending on the client's needs, we may need to train them on how to use and maintain the program. If the Client doesn't have their own RPA Engineer, naturally, we do not need to provide training.
   2. Once the Client expresses their acceptance of the program, both parties proceed with the Product Acceptance, which includes signing the Product Accepance Ducuments and making payments according to the contract.
7. Experience Summary

   1. The Team compiles and summarizes the management and technical experiences gained during the project to create or update documents that can used as a reference for similar projects in the future.
8. Program Maintenance

   1. If the Program Maintenance service was promised in the contract, then, during the agreed-upon maintenance period, the Maintenance Engineer (who may also be the Implementation Engineer) will be responsible for:
      1. Adapting the UI operation logic if any changes in the UI related to the business process affect the normal functioning of the program;
      2. Modifying the data manipulation logic if the data format has changed;
      3. Accommodating the client's new requirements if they are easy to complete and within the Maintenance Engineer's authority. The Maintenance Engineer can directly update the program to meet the client's needs. However, if the changes require significant effort (involving many analysis, design, and implementation), the sales team may need to be involved in signing an addendum to the contract and negotiating additional payment.
   2. As the Program Maintenance period nears its end, we need to contact the client to discuss whether to extend the maintenance period or to end the maintenance service.

## 2.2. Explanation of Terms

* Man-Days: A method used to measure the amount of work involved in a project. One man-day typically represents the workload of an engineer in an 8-hour workday (the legal length of a work day).
* Unit Testing: Testing a small part of the entire program (such a function, a block in UiBot, a workflow, a sequence, or a flowchart in UiPath and Encoo). The goal is to determine whether that specific part of the code is functioning correctly or not.
* Integration Testing: Combining the components that have passed Unit Testing to determine whether they can work together correctly.
* System Testing: Conducting a comprehensive test of the program in the environment it is intended to run in, in order to determine whether it meets all the requirements.
* User Acceptance Testing (UAT): Before delivering the program, the client tests it  to determine whether it functions in accordance with their expectations.
* Party A: The party that expresses their requirements and pays for the project during its duration.
* Party B: The party that fulfills Party A's requirements and receives payment during the project's duration.

# 3. Requirements Change Control (Demand Management)

During the development of a project, we may encounter situations that the client creates or  changes some requirements. An efficient management process should allocate some attention and time to managing those changes of the client's requirements.

Before I explain the reason, let's first acknowledge these prerequisites:

* The payment is agreed upob by both the Party A and Party B, and it's usually calculated using man-days. For example, a project involves a Project Manager, some Senior Engineer, and some Junior Engineer. We need to calculate how many days each engineer would work on the project, and then determine a specific payment and the deadline for delivering the final product.
* Once we determine the scope of the project, we could provide a reasonable estimate of the man-days required.
* Before Party A declares that the project is completed,  the fewer man-days Party B spends,  the greater the profit they gain.

Thus, the reasons we should manage requirement changes can be summarized as follows:

* Maintain clear project scope and reduce project risks

  * An increase in the project typically means that we need to spend more man-days than initially planned, and the new requirements may not have undergone any feasibility verification. As a result, this may introduce unknown risks and increase the costs for Party B (which translates to decreased profits).
* Ensure the project deadline isn't delayed, maintain the project quality, and enhance client satisfaction:

  * Requirement changes can lead to alterations in the previous program designs, affecting the final quality and deadline of the project.
  * Communicate with the client about the new risks, the potential for deadline delays, and the feasibility of requirement changes to gain their understanding and support. This will reduce the likelihood of the client feeling dissatisfied.
* Maintain team morale:

  * Frequent requirement changes can often lead to a decline in team morale,as team members may feel that their efforts are wasted.

Now that we have known the importance of Requirements Change Control, we can implement it as follows:

1. When the project starts, we identify the individuals from both sides who have the authority to propose and approve requirement changes.

   1. To prevent anyone from interrupting the project and hindering its efficient progress, it's necessary to establish the relevant rights and responsibilities at the beginning of the project.
   2. Communicating through designated individuals can help reduce the extra costs that may arise due to varying levels of knowledge between both parties during communication.
   3. Suggested criteria of individuals：

      1. The individual for raising requirements in Party A: It's generally recommended to select a person who is responsible for every aspect of Party A's business, or who can efficiently communicate with all relevant operational staff . This aims to reduce the likelihood that the user feels the program performance does not meet their expectations during the User Acceptance Testing (UAT) period.
      2. The individual responsible for deciding requirements in Party A: It's generally recommended to select a person who is authorized by the Party A Leader, or the Party A Leader themselves.
      3. The individual responsible for raising and determining requirements:

         1. For medium to large-sized projects requiring multiple implementation engineers, it's suggested to appoint a Requirements Specialist. The Specialist is responsible for communicating with the client and documenting the Requirements Book. The Implementation Engineers develop the program based on the Program Design and Requirements documents, if they encounter any questions (such as unclear or difficult-to-achieve requirements), they will communicate with the Requirements Specialist. After the Requirements Specialist fully understands the issue, the Specialist will communicate with the indivaidual responsible for Demand Management.
         2. For small-sized projects, it's acceptable of the Implement Engineer to take charge of requirements communication and determination.
2. Determine the cost of each requirement change

   1. Every time the Client raises some requirement changes, we should determine the cost for the change:
      1. Time cost
      2. Effects on program quality
      3. Potential unclear risks leading to a delayed deployment deadline
   2. Determining the cost is not for requesting additional payments (of course, obtaining more payments is better), but for gain the understaning and forgiveness from the Client for program quality issues and deadline postponements caused by requirement changes. Even if we request more payments or the project performance does not meet the Client's expectations, they generally understand the hard work to some extent.
3. Record every requirement change in documents

   1. For requirement changes that are still under discusstion, have been approved or have been denied, we should record them in documents to the extent possible. If conficts arise with the Client, these records can be serve as evidence for determining both sides' responsibilities.
   2. It's recommended to utilize online ducuments in instant communication software. They are easy for both sides to check, edit, and export as part of project delivery documents.
   3. The format for requirement change documents can be referenced as follow:

| Record Date | Category             | Workflow   | New Description | previous Description | Man-days Estimate | Proposer | Status    | Confirmer | Notes |
| ----------- | -------------------- | ---------- | --------------- | -------------------- | ----------------- | -------- | --------- | --------- | ----- |
| 20XX-XX-XX  | Requirement Addition | Workflow A |                 |                      |                   |          | Confirmed |           |       |
| 20XX-XX-XX  | Requirement Change   | Workflow B |                 |                      |                   |          | Pending   |           |       |
| 20XX-XX-XX  | Requirement Change   | Workflow B |                 |                      |                   |          | Denied    |           |       |

# 4. Risk Management (to be translated)

## 4.1. Risk Identification (to be translated)

## 4.2. Risk Follow-up (to be translated)

## 4.3. Overview of Common Risks (to be updated)

# 5. Stakeholder Management (to be updated)

# 6. Program Design (to be updated)

# 7. License

[MIT License](./LICENSE "开源许可证")
