---
layout: page
title: BOB's Journey to Adminship
subtitle: Exploring the world of Wikipedia Requests for Adminships
cover-img: /assets/img/GDELT-GKG-2016-2018-Outlink-Graph-Random10KAll-6K-Thick.png
thumbnail-img: /assets/img/GDELT-GKG-2016-2018-Outlink-Graph-Random10KAll-6K-Thick.png
share-img: /assets/img/GDELT-GKG-2016-2018-Outlink-Graph-Random10KAll-6K-Thick.png
use-site-title: true
---

# Background and motivation

![title](assets/img/ADA.png)
Wikipedia, the world's largest online encyclopedia, relies on a community of dedicated contributors to maintain and improve its vast repository of knowledge. Admins (short for administrators) play a crucial role in this ecosystem by overseeing the platform, ensuring its integrity, and facilitating a collaborative and respectful environment for editors. The process through which individuals become administrators is known as the Request for Adminship (RfA). Adminship is not just a privilege but a responsibility, and those seeking this role are expected to have a deep understanding of Wikipedia policies, guidelines, and a history of constructive contributions. All the admins have the ability to delete pages, protect pages from editing, and block users, among other tools. Those tasks necessitate a high level of trust from the community, hence, the importance of robust votation in Wikipedia's administrative elections cannot be overstated. They need to ensure a fair and equitable system. A diverse voter base ensures a variety of perspectives, mitigating the risk of undue influence or bias. In short, the votation process is a crucial mechanism for upholding fairness, transparency, and community consensus.

In an ideal world, candidates should be driven by a commitment to actively engage in the governance structure of Wikipedia. On the other side, voters, like Bob, should have for objective to 
ensure that candidates are selected based on their merit, experience, and dedication to the fundamental principles of Wikipedia. However, from 2003 to 2013, there was an average of 53 votes per election out of the millions of registered users[^1] allowed to vote. This low turnout raises questions about the fairness and integrity of the system.

[^1]: Wikimedia, [number of registered users 2003-2013](https://stats.wikimedia.org/#/en.wikipedia.org/contributing/new-registered-users/normal|bar|2003-01-28~2013-05-01|~total|monthly)

In this data story, we aim to address the following questions:

- Is the election process as fair as it should ideally be?
- What drives people to vote?
- How could the Wikipedia democratic process be improved?

Our aim is to investigate the factors influencing participation and identify the challenges that arise from the low engagement rate. Based on our research, we intend to propose solutions to increase the participation rate.

Before we dive into the data, let me introduce you to Bob. Bob is an avid Wikipedia user. Having spent countless hours contributing to Wikipedia articles, he is now considering applying to become admin. However, he's a careful observer who wants to maximize his chance of being elected. Hence, he wants to know more about the voting habits before applying.

Throughout our data story, Bob will serve as our guide, asking important questions about the election process, voter motivations, and potential improvements. So, let's join Bob on his journey of exploration and discovery.


# The data used

## Wikipedia Requests for Adminship (Wiki-RfA)

Our main dataset, the [Wiki-RfA](https://snap.stanford.edu/data/wiki-RfA.html)[^2], spans from 2003 to 2013, and includes a collection of 11,381 users involved in RfA processes, resulting in 189,004 unique voter/votee pairs and 198,275 votes. This dataset offers a detailed view of Wikipedia's community dynamics, reporting each vote, election outcome, and user comment.

[^2]: Robert West, Hristo S. Paskov, Jure Leskovec, and Christopher Potts: Exploiting Social Network Structure for Person-to-Person Sentiment Analysis. Transactions of the Association for Computational Linguistics, 2(Oct):297–310, 2014.

## Complete Wikipedia Edit History (Up to Jan 2008)
Our second dataset, the [Complete Wikipedia Edit History](https://snap.stanford.edu/data/wiki-meta.html)[^3], provide a complementary perspective. This dataset is a vast repository containing several terabytes of text, capturing the entire edit history of Wikipedia articles up to January 2008. It is divided into several components, showcased in the following table, each representing different facets of Wikipedia.

| File                           | Description                         | Size (compressed) |
| ------------------------------ | ----------------------------------- | ----- |
| Main Namespace Revisions       | Core Wikipedia articles             | 8Gb   |
| Talk Namespace Edits           | Article discussion pages            | <1 GB |
| User Page Revisions            | User personal pages                 | <1 GB |
| User Talk Page Edits           | User discussion pages               | <1 GB |
| Wikipedia Namespace            | Administrative procedures and pages | 3Gb   |
| Wikipedia Namespace Talk Pages | Administrative discussion pages     | <1 GB |

In this project, the focus was on the Main Namespace Revisions and User Talk Page Edits to track and analyze user interactions. The former enables us to consider interactions between users outside of the election process. We consider an interaction between two users as an edit from one user to another user’s talk page (a personal page used to discuss with other editors). Those interactions reflect direct, personal and conscious interactions. This allows us to link voters and candidates outside of the elections, to identify who has had interactions. The latter comprises the edits on different Wikipedia pages. From that, we can gather information on the centers of interest of the users.

[^3]: J. Leskovec, D. Huttenlocher, J. Kleinberg. Governance in Social Media: A case study of the Wikipedia promotion process. AAAI International Conference on Weblogs and Social Media (ICWSM '10), 2010.

# Datasets Exploratory Data Analysis
**TODO**














# Elections Dynamics
## Individual perspectives in RfA Elections
**TODO**

## Hidden Structures: Communities and their Impact on RfA Elections in Wikipedia
Bob has interacted a lot throughout his Wikipedia journey with other users. He perceives himself as a member of a small intellectual community, bonded by similar interests. He is very curious to know whether his community will have an impact on his election and, if so, what kind of impact it might have.

Indeed, the influence of communities – often subtle, sometimes unseen – may play a crucial role in shaping the outcomes and the turnout of these elections. At the core of these unseen communities lie the personal talk pages of Wikipedia users, a virtual place where individuals engage in conversations, share insights, and negotiate differences. These personal talk pages serve as a unique space, reflecting concrete and direct interactions between users.

By taking the unique lens of focusing on the personal talk pages to build communities, we aim to find potential revelation of systemic unfairness, as certain communities may coordinate to cast negative votes, introducing an element of bias into the electoral process. Our investigation extends to examine whether users tend to cast their votes only to support their community and whether certain communities exhibit a pattern of negative voting towards one another.

Commencing our analysis, we construct a graph illustrating interactions on personal pages. Each node represents a user involved in an election interaction, and an edge is established if two users have engaged on their respective personal pages. The graph, undirected and weighted by interaction frequency, undergoes partitioning into communities using the Louvain method. The resulting graph highlights 29 distinct communities as shown on the following image.

![community_graph](assets/img/community_graph.png)

Now that we have identified 29 communities, analyzing the content edited by each community presents an exciting opportunity. By scrutinizing the content they engage with and the topics they choose to edit, we can gain a deeper understanding of what binds each community together. The goal is to dissect the content edited by each community and use this information to better understand the motivations of each vote. The following dropdown menu shows the 20 most edited pages for each community.

<iframe src="assets/html/menu.html" width="750px" height="530px" frameborder="0" position="relative">Genre plot</iframe>

Analyzing the menu above, it becomes evident that, while the majority of edited pages are centered around American culture, distinct focal points of interest emerge for each community.

Now that Bob knows that communities exist, it remains to know if his own community will be a precious support in his upcoming election. Let’s investigate this mysterious voting influence within and between communities.

For each community, let $p_i$ be the fraction of Wikipedians inside the community. If we take two random users, the probability that they are in the same community is $p_{\text{same}} = \sum_{i \in C} p_i^2$. If the votes are distributed at random, this corresponds to the probability that the voter and the candidate are in the same cluster. The expected number of intra-cluster votes with this model is $p_{\text{same}}*T$, where $T$ is the total number of votes.

With those communities we observe that 25.96% of the votes are intra-cluster, in stark contrast to the expected value of 7.52%. This difference strongly indicates a trend toward engaging more in elections for individuals with whom there has been an interaction at some point.

To make it more general, we compute the numbers of votes from each community to every other community and normalize these values by the corresponding expected numbers of votes based on community sizes. The matrix presented here highlights the significance of votes within the same community, as these values consistently exceed those of inter-community voting.

![shades_of_blue](assets/img/shades_of_blue.png){: width="2000"}

The existence of specific community interests or perspectives may lead to biases in voting behavior, favoring candidates aligned with particular groups over others based on shared ideologies.

The presence of those communities within Wikipedia introduces significant challenges for the fairness of the electoral process. Intra-community favoritism may exist as seen above, members of a community may be more inclined to positively support candidates from their own group, potentially disregarding individual qualifications or merits. In consequence,  certain communities, particularly those more active or influential, may dominate the electoral outcomes, sidelining the perspectives of less prominent groups. Furthermore, the emergence of negative voting dynamics among communities might appear between communities that share different ideas. This undermines the democratic ideals of the Wikipedia election process. 

To detect the presence of such behavior, we examine the ratio of positive votes between pairs of communities, comparing it to the baseline ratio derived from the entire dataset. The graph below displays only those results that show statistical significance (at the 0.01 level) when compared to this standard. Green arrows denote communities that statistically vote more positively for each other, while red arrows signify communities that exhibit a lower positive vote tendency toward each other. Additionally, the size of each point in the graph is proportional to the size of the community it represents.

<iframe src="assets/html/graph_daniel.html" width="750px" height="530px" position="relative">Genre plot</iframe>

We can denote that for all the groups that have a self-loop, this latter is green. Half of the groups have this arrow. This brings evidence for intra-community favoritism. We also see clear signs of negative voting dynamics. The most telling is “Pop culture mix”. This community is mostly made of Pop Culture and People magazines topics. Some examples are “David Beckham”, “Britney Spears” and “Paris Hilton”. We can make the assumption that those topics are not seen as serious enough by the Wikipedia community or that its community may consist of more novice users. For that reason, we observe a consequent number of negative arrows pointing towards this community. Some votes also have a cultural influence. We observe “Balkans and Central Asia” voting positively towards “Russia and Eastern Europe”. And some votes open the door for interpretation. “Religion Debates and Controversies” not supporting “Youth Pop Culture” can be interpreted as a way for Religion to contest the society in which youngsters live. This already gives us an idea of the motivation behind votes.

As an Australian, Bob is delighted with these results. Now, armed with the knowledge that he can anticipate strong support from his community, he also finds assurance in the absence of any indications of animosity between the Australian community and any other group.

# Conclusion

**TODO**

# Suggested Solutions
To strengthen the democratic process, our objective is to enhance voter participation, particularly among individuals who may not typically vote for each other. We aim to provide persuasive reasons for users to engage in the voting process, especially when they are unfamiliar with a candidate or lack a direct connection. Our proposed solution involves sending well-timed invitations to random users, encouraging their participation in specific elections. The strategic use of invitations aims to motivate users to cast their votes and we introduce an element of randomness to diversify the pool of voters. Consequently, it reduces the impact of a given community on the overall outcome.

To further incentivize participation, we recommend offering rewards to users who actively participate in voting. These incentives could take the form of unlocking exclusive items for personal use on their profiles, providing an additional motivation for users to engage in the voting process.

To facilitate the voting process and ensure the meaningfulness of each vote, we propose accompanying each invitation with an explanatory note about the candidate. Drawing inspiration from Wikipedia's well-established [guide for voters](https://en.wikipedia.org/wiki/Wikipedia:Advice_for_RfA_voters), we suggest leveraging Wikipedia's resources to provide a concise summary along with various statistics on the candidate's contributions. This approach significantly reduces the effort required for voters to make informed decisions.

By implementing these solutions, our goal is to diminish the influence of support based on existing connections or shared interests, promoting a more impartial and equitable voting process. Additionally, we anticipate that this approach will lead to increased voter turnout, thereby enhancing the overall fairness of the system.
