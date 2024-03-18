# FABRIC for education: best practices and resources for teaching with FABRIC

Welcome! If you are looking for the materials from the education tutorial at the FABRIC KNIT Community Workshop, you're in the right place.

**Getting extra help**: If you are an instructor that needs help planning your use of FABRIC, please post in the [FABRIC educators forum](https://learn.fabric-testbed.net/forums/forum/fabric-educators/). You may also contact the author of this tutorial: [Fraida Fund](mailto:ffund@nyu.edu).

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

you will also need to consider whether resource availability is likely to be a problem. If you have a large course enrollment, you will not be able to support simultaneous use of "scarce" non-virtual resources like GPU, FPGA, and SmartNIC interfaces for all students. (If you try to do this anyway in a large class, it will be a frustrating experience for your students, since they are likely to struggle to get the resources they need to complete their work.) However, if you have a small number of students and use of these "scarce" resources is *necessary* for your course topic, you may request to have extra permissions added to your course project.


### Before your course: immediate preparation 

Before your students use FABRIC for the first time in your course, you have some logistics to take care of:

- [ ] **Run through all of your FABRIC assignments to test them (again).** Even if you have previously used the materials you plan to use, things may change. For example, you may need to update a FABRIC API call, or you may need to change a command because the latest version of a software package requires it.
- [ ] **Request a project for your course.** Use the [FABRIC class request form](https://fabric-testbed.atlassian.net/servicedesk/customer/portal/2/group/11/create/64) to set up a project for your course. At this stage, you will need to already know about the types of resources the materials you are using will require (as discussed above). 
- [ ] **Have a support plan in place.** Your students are likely to have questions or encounter problems as they use FABRIC, and you need a plan in place for your course staff to support them. Make sure to communicate to students "what you should do if you have a question or problem while working on these assignments".
- [ ] **Assign ["Hello, FABRIC"](https://teaching-on-testbeds.github.io/hello-fabric/) and add students to your project**. This process involves some iteration - you need your students to request accounts, then you need to add them to your projects once their accounts exist on FABRIC, and then they can continue with setting up their accounts. You should manage this timeframe carefully, with deadlines for your students to (1) initiate the process of creating a FABRIC account, and (2) follow up within 24 hours using the link they received by email to finish creating a FABRIC account, so that you will be able to bulk-add students to the project all at once.

You should also prepare yourself and your course staff for the issues that students are *likely* to encounter, so that you recognize them and are prepared to assist when they come up. Common issues include:

* trying to run experiments without having finished "Hello, FABRIC". You can recognize this from the output of the `fablib.show_config()` command near the top of most FABRIC Jupyter notebooks. Even if a student has previously completed "Hello, FABRIC," they sometimes try to "fix" problems later by changing their FABRIC configuration or removing their keys, in which case they may need to repeat "Hello, FABRIC."
* executing cells out of order or skipping cells in a Jupyter notebook. You can recognize this by checking the execution count next to each cell in the notebook.
* problems with SSH and SCP. Many students have limited experience with key-based authentication, and this is exacerbated by the extra bastion host hop required by FABRIC. You may find it easier to have students use the shell in the FABRIC Jupyter environment for SSH, which is configured as part of "Hello, FABRIC," rather than their own local terminals. You can encourage students who are reporting SSH problems to show you the output of their `ssh` command with the `-v` flag added, for more verbose output, in order to help them identify the problem.
* infrastructure issues, e.g. temporary outages (planned or unplanned). Your students do not have the experience to differentiate between an infrastructure problem and user error, and they are likely to attribute *all* issues to infrastructure problems. You and your course staff should subscribe to the [FABRIC announcements](https://learn.fabric-testbed.net/forums/forum/fabric-announcements/) forum to make sure you are aware of any infrastructure problems, so you can in turn let your students know.
* trying to re-create a slice that already exists OR trying to use a slice that is already expired.
* expired keys.

### While students are actively engaged with materials


### Afterwards

## Ready-to-use learning materials for teaching on FABRIC


#### Basic setup/skills

For many students, the first interaction with FABRIC will be [Hello, FABRIC](https://teaching-on-testbeds.github.io/hello-fabric/). Other "skills"-focused exercises include:

* [Hello, Linux](https://teaching-on-testbeds.github.io/blog/hello-linux)
* [Inspecting network traffic with tcpdump and Wireshark](https://witestlab.poly.edu/blog/wireshark-tcpdump/)


### Tutorial examples

#### TCP congestion control

This example shows how the same activity can use different "interfaces" to FABRIC, with very different effect.

In both versions of this example, students will use a Jupyter notebook to reserve resources on FABRIC and configure them. Also, the students in both cases use the Jupyter notebook to visualize the results.

However, 

* in one version, students just run cells and observe the output: [TCP congestion control](https://github.com/teaching-on-testbeds/tcp-congestion-control)
* in the other version, students log in to resources over SSH and execute commands on them, and observe the output: [TCP congestion control](https://witestlab.poly.edu/blog/tcp-congestion-control-basics/)

#### Load balancing and dynamic scaling on K8S

This example about [deploying machine learning systems to the cloud](https://github.com/teaching-on-testbeds/k8s-ml/blob/main/README.md#onboarding-for-fabric-users) is a more advanced cloud computing sequence that students may run on FABRIC, leading to an open-ended design challenge. It also serves as an example of an education use case that requires "more" than the standard resources:

* this experiment runs only on FABRIC sites that have an IPv4 management network, so it will not work on EDUKY-only projects. 
* this experiment requires the `VM.NoLimit` permission on the FABRIC project. To allow students to explore a wide variety of deployment strategies taking resource usage into account, every student will use 3x VMs, each having 4 VCPUs, 8 GB memory, 40 GB disk space.
* on FABRIC, students cannot view the web service they are hosting in their own browser, unless they set up an SSH tunnel. The FABRIC `Net.FABNetv4Ext` and `Net.FABNetv6Ext` are not permitted for education projects, for security reasons.

Some notes about running this experiment:

* you can try it out without first training your own model! There is a base model that is already provided, if you choose to skip that step.
* the setup stages for this experiment (setting up a Kubernetes cluster) take 10-20 minutes (unattended) to run.
