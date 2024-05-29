# DAO Classification

Authors:

**Ari Kimelman: Kimelmanari@gmail.com**
**Jona Weishaupt: weishaupt.jona@gmail.com**
**Priyanshu Yadav: priyanshu.yadav.152@gmail.com**

## Introduction

This project was produced with The Nova School of Business and Economics Data Science Knowledge Center by students Jona Weishaupt, Ari Kimelman, and Priyanshu Yadav. The professors supervising this research were Susana Lavado, Joao Oliveira, and Daniel Obermeier.

For more information about NOVA SBE Data Science Knowledge Center see the link below.
https://www.novasbe.unl.pt/en/data-science/overview

DAOs are a new method of governance that requires decentralized consensus about the changes made to an organization. DAOs are used to govern different types of decentralized applications in Web 3.0 from decentralized financial services to blockchain bridging services. DAOs offer an opportunity to democratize applications removing the need for a trusted party to make decisions on behalf of the users of the application. The efficacy of DAOs has been put into question as DAO participation is typically low and community consensus creates a bottleneck when implementing changes to adjust to market trends. We seek to better understand the degree to which DAOs are in fact decentralized. 

We investigated the degree to which DAOs are decentralized. We measured decentralization using the Gini Coefficient, the amount an individual with the largest voting power contributes to each proposal, and the average number of individuals required to achieve 51% of voting power for a DAO. We also were interested in analyzing trends in centralization and decentralization over time. To do this we evaluated a variety of DAOs using the above-mentioned metrics over time to determine if any insightful trends were discovered. Additionally, plots and descriptive statistics were created to better understand key features of DAO participation.

## Data Source

**Source**

https://zenodo.org/records/10794916

Three Datasets:

1) **deployments.csv -> Information on the DAO**
    Columns:
    a) id
    b) platform
    c) platform_deployment_id
    d) name
    e) website
    f) additional
    g) votes_count
    h) proposal_count
2) **proposals.csv -> Information on the proposal**
    Columns:
    a) id
    b) deployment_id: foreign key to deployments
    c) platform_proposal_id
    d) author
    e) date
    f) votes_count
3) **votes.csv -> information on the votes cast**
    Columns: 
    a) id
    b) proposal_id: foreign key to proposals
    c) deployment_id: foreign key to deployments
    d) platform_vote_id
    e) voter
    f) date
    g) choice
    h) weight


## Using the Notebook

1) Update and upload the required datasets from the source listed above
2) Install the required libraries, DuckDB was used as especially the votes.csv file is extremely large and can lead to inefficies and slow run time with non-optimized queries.
3) Pick a DAO you want to analyze by changing the variable "DAO" in the "DAO Selection and Exploratory Data Analysis" part of the notebook ("DAO = 'Aave')
4) Pick the ID of the DAO from the table after running the cell above, as the DAO could have been on different platforms in the past and edit it into the required spot one cell below the previous step. (myDAOs = ['b6c95a58-d36d-5482-9fa0-fffbbed6e20a']) and then edit the id into the SQL statement 
(chosenDAOs = duckdb.query("SELECT * FROM deploymentsdf WHERE id IN ('b6c95a58-d36d-5482-9fa0-fffbbed6e20a')").df())
5) Run the notebook to get the metrics in each part.

## Credits

Peña-Calvin, A., Schwartz, A., Arroyo, J., & Hassan, S. (2024). Concentration of Power and
Participation in Online Governance: the Ecosystem of Decentralized Autonomous
Organizations. Companion Proceedings of the ACM Web Conference, 13–17, 2024,
Singapore, doi: https://doi.org/10.1145/3589335.3651481


