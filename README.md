# FABRIC for education: best practices and resources for teaching with FABRIC

Welcome! If you are looking for the materials from the education tutorial at the FABRIC KNIT Community Workshop, you're in the right place.

**Getting extra help**: If you are an instructor that needs help *planning* your use of FABRIC, please post in the [FABRIC educators forum](https://learn.fabric-testbed.net/forums/forum/fabric-educators/). You may also contact the author of this tutorial: [Fraida Fund](mailto:ffund@nyu.edu).

## Many ways of teaching with FABRIC

To minimize pain for your course staff (yourself, and any TAs you might have working with you) and for your students, it is important to recognize that there are many ways to teach with FABRIC, and you should carefully select the way that is right for *your* course.

For example, there any several "interfaces" that students could have with testbed resources. On a scale from "requires the least expertise" to "requires the most expertise", these are:

* they may run a Jupyter notebook that gets resources, configures them, and executes the experiment on them. Students just run cells and observe the output.
* they may run a Jupyter notebook or use the Slice Builder to get resources, then log in to resources over SSH and execute commands on them, and observe the output.
* they may have to *write their own* Jupyter notebook to get resources and configure them, then execute the experiment on them.

There are also different ways in which you can support students in their FABRIC experience. On a scale from "most support" to "least support", some of these are:

* use in-person class time with course staff present for students to run FABRIC experiments
* provide a video walkthrough showing what the experiment looks like as a member of the course staff executes and explains the experiment
* offer synchronous office hours with course staff and asynchronous Q&A (on the course LMS, or a platform like Piazza/Ed) to help students resolve problems

The circumstances of *your* course will dictate how you use FABRIC. 

For example, suppose that

* you are teaching an upper-level undergraduate or masters-level course in computer networking,
* you have a very large class, and a few TAs,
* and their level of preparation varies, but most have "touched" Linux before,

Then, you might have students use the SSH interface, where they execute Linux commands on resources directly, so that they get experience with this way of interacting with remote resources. You might choose to provide a video walkthrough so that students can see what each step should look like. In a large class, a video walkthrough can help resolve many questions students might have before they even have them! You could also offer synchronous office hours and asynchronous Q&A for the questions that are not addressed by the video walkthrough. An asynchronous Q&A platform where every student can see all of the questions and answers - even the ones they didn't post themselves - can help minimize pain for course staff in a large class.

On the other hand, if 

* you are teaching a course for non-majors about "how the Internet works",
* you have a small class and one TA,
* and many students have no meaningful computing background,

you would probably prefer the "students just run cells and observe output" interface. However, you anticipate that some of your students will struggle with this, so you might choose to use in-person class time for "FABRIC assignments" so that you can help with issues as they come up.

Finally, if

* you are teaching an advanced projects course,
* it is a small class and you have no TA,
* students are expected to have some level of independence

then you might expect students to write their own Jupyter notebooks, and to visit office hours if they need help.

## How to minimize pain for course staff and students

### First steps: planning your use of FABRIC

At least a few weeks before you plan to use FABRIC in your class, you should begin to plan your use of FABRIC by answering some questions.

#### What do you want students to learn/do? 

You need to decide what technical skills you want your students to use as part of their FABRIC experience.

* Do you want students to practice designing new experiments and realizing them on FABRIC? (This might apply e.g. in an advanced projects course)
* Do you want your students to learn and practice the use of standard Linux utilities? (This may apply if you are teaching an upper level computer science course)
* Do you want your students to focus exclusively on concepts, not technical skills? (This may be the case if you are demonstrating an idea to non-CS-majors)

#### Are these existing materials you can use?

Then, think about the topics that you want to include in your students' FABRIC experience. There are existing ready-to-use materials for various topics in computer networks, network security, cloud computing, and related fields.  You may be able to find existing materials that you can use as-is or adapt for your class.

This is also the right time to think about the resources on FABRIC that will be available to your course. Most education users of FABRIC are expected to exclusively use small-scale virtual resources on the dedicated EDUKY site. If the existing materials you want to use require other resources - 

* larger VMs (more cores, RAM, and disk space)
* public IP addresses
* GPU, FPGA, SmartNIC

you will also need to consider whether resource availability is likely to be a problem. If you have a large course enrollment, you will not be able to support simultaneous use of "scarce" non-virtual resources like GPU, FPGA, and SmartNIC interfaces for all students. However, if you have a small number of students and use of these "scarce" resources is *necessary* for your course topic, you may request to have extra permissions added to your course project.
