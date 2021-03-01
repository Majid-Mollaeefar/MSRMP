# Multi-Stakeholder Risk Assessment Tool

It is a risk assessment tool that assesses the risk exposure levels in a multi-stakeholder manner for a given system. The tool has a two-fold purpose, (I) Evaluate and quantify risk levels for all involved stakeholders, and (II) Solving the risk minimization problem, which is a multi-objective optimization problem.  
This tool works based on JSON file, all inputs and outputs. Before using the tool, we invite you to read the documentation files (see Documents Section) in order to have a clear view of how this tool works. The documents are the research papers that define the Multi-Stakeholder Risk Minimization Problem and solve this problem.


## Requirements
```
-Java 8 or higher
-Scala SDK V.2.13.2
-JavaFx SDK V.11.0.2 (for plotting the result)
-Gson library V.2.8.6 
```
## How to use
```
1. Clone the project
2. Import project into your desire IDE (our recommendation is IntelliJ IDEA)
3. Define or import input files (i.e., adding the needed JSON files, such as Threats, Goals, etc.)
```
## Description of the tool
The tool is divide into two main phases, 1) Risk evaluation 2) Optimization.

For the first phase, you need to define three JSON files (`Threats`, `Goals`, `Stakeholder`) as input artifacts and three other JSON files as can be considered association actions (`Threat_Impact`, `Threat_Controls`, `Threat_Affected`) , and for the second, you need one additional JSON file which is `Threat_Existence`. 
You can either create the input JSON files manually, according to the existing example in the clone project *(jsonFiles folder)* and its files structures, or automatically. For manually way, you just need knowledge about JSON file structure which you can follow the sample files in *jsonFiles folder*. For automatically, you need to follow the following steps:

**Note:** All classes mentioned below are defined in the *action folder*.

1. Define Threats: In order to define the list of threats in your system you can run following java class then define number of threats and their name through the console. 

```Java
Run ThreatDetermining.java 
```
2. Define Stakeholders and their impact Criteria: The involved stakeholders in the analysis and their impact criteria define in the Stakeholder JSON file. For example, a stakeholder can be *Data subject*, and *Social situation, Individual freedom, Health condition and Financial situation* are its impact criteria.
```Java
Run StakeholderDetermining.java 
```
4. Define Protection Goals: The protection goals specify in the Goal JSON file, for example, *confidentiality, integrity, and availability*.
```Java
Run GoalDetermining.java 
```
5. Define Threat-Protection Goal Association: Through this action, you can specify the association between threats and goals in other word, each threat affect which protection goals. For example, Unauthorized access affects confidentiality and integrity protection goals.
```Java
Run ThreatGoalAssociation.java 
```
6. Define Threat Impacts: According to their impact criteria, the impact level of each threat for all involved stakeholders determines in Threat_Impact JSON file. In fact, in this action, the risk analyst assigns an integer value to the aversion level that each stakeholder is considered to have against each threat, according to his/her criteria.
```Java
Run PreferenceImpacting.java 
```
7. Define Threat Existence values: This JSON file needs for perfoming optimization where you must define all possible threat existence values for each threat.

In order to perform optimization and plot the result , after providing all these JSON files, you just need to Run `` RunOptimization.java `` class from *optimization folder*.


# Documents
This tool is part of following research papers:
1. Multi-Stakeholder Cybersecurity Risk Assessment for Data Protection [SECRYPT 2020](https://www.researchgate.net/profile/Majid_Mollaeefar2/publication/342887924_Multi-Stakeholder_Cybersecurity_Risk_Assessment_for_Data_Protection/links/5f0c0e5aa6fdcc4ca4662b8f/Multi-Stakeholder-Cybersecurity-Risk-Assessment-for-Data-Protection.pdf).
2. Identifying and Quantifying Trade-offs in Multi-Stakeholder Risk Evaluation with Applications to the Data Protection Impact Assessment of the GDPR [Underwriting]
