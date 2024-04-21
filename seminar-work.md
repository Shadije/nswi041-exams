# Student information system - Exams

The Student Information System (SIS) Exams Module is an integral component of the university's academic infrastructure, designed to streamline the management of examination-related processes for both students and faculty. This module provides a comprehensive platform to efficiently administer, schedule, monitor, and evaluate exams, ensuring smooth operations during the assessment period.

## Functional Requirements

This section specifies the functional requirements.

### User requirements

**Students**
- If an exam is full, I should be able to put myself in a waiting queue that will automatically sign me up for the exam if a spot opens up, because I do not want to check it too often.
- I should be able to view my exam schedule/calendar, because with a lot of enrolled exams, a list view may be disorienting.
- I should be able to filter available exams based on the course they belong to, and whether I have already passed them, because it will be less distracting for me.
- As a student, I should be able to enroll in exams and assessments because I need to fulfill my academic requirements.
- As a student, I should be able to view my examination results as soon as they are published because I want to keep track of my academic progress.
- As a student, I should be able to view my examination history, including past scores and feedback, because I want to evaluate my academic performance over time.
- As a student, I should be able to download or print my exam results for my records because I may need them for personal documentation or verification purposes.
**Teachers**
- I should be able to kick out enrolled students automatically if they have not yet fulfilled criteria needed for the enrollment (e.g. credit), because it will be tedious to do so manually.
- As examiner, I should be able to publish exam results efficiently because it is essential to provide timely feedback to students.
- As examiner, I should be able to manage the enrollment lists for the courses I am teaching because I need to prepare for the assessment process accordingly.
- As examiner, I should be able to provide detailed feedback on student performance because it helps students learn from their mistakes and achievements.

### System requirements

#### Actors

[*Document here all actors from the use case diagrams. Make a subsection for each actor and their short description in each subsection.*]

##### [*Actor name*]

[*Actor description*]

#### Use cases

[*Document here all use cases. Create a subsection for each use case diagram. If you have only one use case diagram, you do not need a special subsection.*]

##### [*Use case diagram title*]

[*Use case diagram in PlantUML*]

```plantuml
@startuml
left to right direction
actor Student as s
actor Teacher as t
usecase "Sign in" as SI
usecase "Get credit" as GC1
usecase "Enqueue for waiting list" as QWL1
usecase "View exam calendar" as VEC1
usecase "Filter exams" as FE1
usecase "View exam result" as VER1
usecase "Sign out" as SO1
usecase "Kick student out" as KSO1
usecase "Publish result" as PR
usecase "Make/create exam date" as MED
usecase "Change exam date&time" as CED
usecase "Not pass exam" as NPE
usecase "Pass exam" as PE
 
s --> GC1
s --> QWL1
s --> VEC1
s --> FE1
s --> VER1
s --> SO1

VER1 --> NPE : <<include>>
VER1 --> PE : <<include>>
GC1 --> SI : <<include>>
VEC1 --> SI : <<include>>
FE1 --> SI : <<extend>>
QWL1 --> SI : <<extend>>
MED --> SI : <<include>>
PR --> VER1 : <<include>>
PR --> VER1 : <<include>>
MED --> CED : <<include>>

t --> KSO1
t --> PR
t --> MED
@enduml
```

To be able to embed PlantUML diagrams to Markdown code with previews in VSCode you need
* Markdown All in One extension
* PlantUML extension
View > Command Pallete... > Markdown All in One: Print current document to HTML

Follow https://plantuml.com/

[*Describe the diagram in a short paragraph. Describe each use case from the diagram in the detail from the lecture in a separate subsection.*]

###### [*Use case title*]

[*Use case description in the structure from the lecture.*]

[*Add an activity diagram for one use case per a team member*]

Queue:
Detail:
Happy path - The student is waiting in the queue until vacancy occurs. Then is automatically enrolled on the exam and given a specific time. 
Alternatives: 
The student will not be able to enroll to the exam because the capacity is full.
The student is not able to get to the queue because the student has not fullfilled the requirements for enrolling for the exam.
Prerequirements:
The capacity is full.
It is still possible to enroll for the exam.
Postrequirement
To be able to see the position in the queue.

Enroll for exam:
Detail:
Happy path - Student is enrolling for a specific date and subject.
Alternatives: 
Can happen that there is no way to get enrolled for the specific date or time.
The term can be full.
There is no term that the student will be satisfied with
Prerequirements:
To have credit for this subject
The term is opened for enrolling
There is a term that is opened and is not full
Postrequirements:
To be succesfully enrolled to the term

Get credit:
Detail:
Happy path - To meet the criteria for acquiring the credit for the subject which is later granted to the student from the teacher
Alternatives: 
Not having enough points the acquire the credit for the subject
Not having submitted credit work before deadline
Prerequirements:
To meet the criteria for acquiring the credit for the subject
To be enrolled for the subject
Postrequirements:
Permission to be able to enroll for the exam

Filter exams:
Detail:
Happy path - to choose from options that are available
Alternatives: 
There is no term of exam that meets the criteria
There are no terms for the exam listed yet
Prerequirements:
List of terms for the exam
To be enrolled for the subject
Postrequirements:
The list of all the terms for the exam that meets the criteria from the options available

Pass exam:
Detail:
Happy path - To pass the exam to be awarded with passing of this course
Alternatives: 
Not to have enough points for passing the exam
Prerequirement:
To be enrolled for the specific exam date that you are taking
Postrequirement:
Completing the subject and passing the exam you enrolled.

Unenroll from exam:
Detail:
Happy path- Successfully unenroll from the exam.
Alternatives: 
It is not possible to unenroll from the exam anymore.
Prerequirement:
To be enrolled for the exam. 
Postrequirement:
Have the oportunity to enroll for another date or time. 



## Information model

[*Express the information model of the domain as a UML class diagram in PlantUML. Do not use class methods in the diagram, only classes, class attributes and associations connecting classes.*]

```plantuml
@startuml
class Car

Driver - Car : drives >
Car *- Wheel : have 4 >
Car -- Person : < owns
@enduml
```

[*Document each class with in a separate subsection*]

### [*Class name*]

[*Class description consisting of its definition, description of its essential properties (attribues and associations).*]
