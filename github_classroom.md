-Feb 12, 2021

# GitHub Classroom
<h6>A critique of GitHub Classroom  </h6> <br>

During this pandemic, the need for technologies that can help in teaching online has increased rapidly. GitHub Classroom is one of the many tools available online that allow teachers to manage and organize their classes. GitHub classroom is a product line released by GitHub in 2015[1]. It can primarily be used for sending out assignments to the students, provide them with the starter code and feedback. It requires the users, which can either be teachers, students, or TAs, to have prior knowledge of how GitHub works and what is it used for.

To use with GitHub classroom, teachers need to work with GitHub and GitHub Classroom in parallel. To start with, teachers and students need to sign up on GitHub. Teachers can then use the same account for GitHub Classrooms to manage their classes. First, an organization is created in GitHub. The organization is nothing but an umbrella under which various classrooms can be created and access to these classrooms can be managed at a higher level. After that, a repository can be created before publishing any assignment. This repository will contain all the starter code which can be used as a base code by the students while solving the assignment. Once this is all set up, teachers can then Sign in to the GitHub classroom and create a classroom by selecting one of the organizations they have created in their GitHub account. While creating a classroom, they also have an option to invite TA's and admins to the organization. Next, a URL(of the classroom) is sent to them to join the classroom. One of the interesting features provided by GitHub classroom is the integration with third-party Learning Management Systems such as Google Classroom, Canvas, Sakai, etc. This integration allows the automatic import of the roster to the class. Alternatives to add student roster could be the manual entry of student's IDs or uploading CSV/text files. After creating the classroom, assignments can be created for that particular classroom. An assignment can be configured by setting the title of the assignment, its deadline (i.e. date & time), and selecting whether it is an individual assignment or group assignment. Teachers can then link their repository that contains boilerplate code with the assignment. There is another interesting feature available that allows teachers to integrate one of the two online IDEs i.e. Microsoft MakeCode or Repl.it with an assignment.


For every student (or group if it is a group assignment) that accepts this assignment, a repository will be created under the student's account. The repository can be public or private as selected by the teacher while creating the assignment.

 ![Image of Attack Model](pics/AttackModel.PNG)<br>
 <b>Figure 1</b>: <i>Attack Model</i>[2]</i>

<h6>[Implementation]</h6> 
The implementation includes Preprocessing of data in Bitcoin Blockchain and Transaction fingerprinting.

* Preprocessing of Data
  * Bitcoin Blockchain is downloaded and its data is parsed using a tool called Armory to retrieve information required to build a graph.
  * A python package called Scrappy is used to fetch information from web forums via a crawler which fetches information from bitcointalk.org in breadth-first manner. Fetched information is verified with data parsed in step 1. The result of this step is the identification of large number of users. Code was run for less than 30 hours and a total of 222 users were identified with their overall 2404 addresses.

* Transaction fingerprinting
  * Matching the roughly overheard transactions with actual transactions in Bitcoin blockchain. The amount is first converted using daily market price from [1]. The overheard amount is compared with an approximation of +- $1 in the blockchain and time of the transactions is approximated to +- 5 minutes. 
 
 <h6>[Graph analysis]</h6> Metrics evaluated from graph analysis are: most important nodes in the network, the assets of these nodes, the movement of assets between nodes, nodes having high number of transactions. <br>
 Transaction graph was created to determine the flow of bitcoins from one public id to another public id. Transaction graph also helped to link multiple addresses to one user.<br>
 User graph was created where each user has all the addresses linked to it. Nodes in user graph representing real users and link between nodes representing the transaction happening between two users. <br>
 
 
 ![Image of Graph Analysis](pics/GraphAnalysis.PNG)<br>
 <b>Figure 2</b>: <i>The graph analysis pipeline that was used to reveal user identity constructs a user network graph
as shown, and annotates the users in the graph with web scraped results[2].</i> <br>


 
 * PageRank algorithm is used to find the some of the interesting users based on their activities and the transactions made by them.
 * User De-anonymization i.e identities of some of the interesting users were revealed.
 
 The analysis was done for transaction occurred on Oct 25, 2013.<br>
 The transaction graph built for that day had 89,806 transactions among 80,030 different public addresses. The user graph had 54,941 nodes with 89,806 edges[2].

  <h6>[Results]</h6> The authors were able to link the transactions associated with SatoshiDICE and Wikileaks. They were also able to link users in forum with nodes belonging to Silk Roads. It is hence proved in the paper that the system is not entirely anonymous.
  
Click [here](https://github.com/sharm76/7570-blockchain/blob/master/Class%20Notes/Monika/papers/Bitcoin%20Transaction%20Graph%20Analysis.pdf) to read the paper.


<h6>[References]</h6>
[1] https://en.wikipedia.org/wiki/Timeline_of_GitHub<br>
[2] Bitcoin Transaction Graph Analysis, Michael Fleder, Michael S. Kester, Sudeep Pillai, 2015
