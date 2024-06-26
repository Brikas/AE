- {{embed ((660ae81b-3f51-41ac-aed0-4653d566c346))}}
- [Using GPT for Market Research.pdf](G:\My Drive\CBS\Thesis\Using GPT for Market Research.pdf)
  collapsed:: true
	- [Academia link](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4395751) - cited by 50+ in 2023
		- [direct lnk](https://www.hbs.edu/ris/Publication%20Files/23-062_b8fbedcd-ade4-49d6-8bb7-d216650ff3bd.pdf)
- 73 cits
- Trivia
  collapsed:: true
	- (Brand J, Israeli, A., Ngwe D., 2023)
	- LLMs as a tool for [[market research]]
	- ((660ae597-6718-4a20-9d80-e06de3097602))
	- #introduction
	  collapsed:: true
		- > GPT’s training data includes information from numerous sources on the internet, which may include product reviews, messaging boards, and other online forums with contributions from a wide range of consumers discussing the products they shop for and purchase.
		- > these components suggest that GPT may be an invaluable source of insight into consumer preferences due to its ability to mimic or replicate human responses.
		- > Existing tools for market research, such as conjoint studies, focus groups, and proprietary data sets can be expensive. If LLMs can generate responses that are consistent with existing studies on human subjects, then they may also be able to serve as a fast and low-cost method of providing the information typically generated by conjoint studies and other customer surveys.
		- Example use
		  collapsed:: true
			- > As major tech companies have begun to combine LLMs with tools for searching and synthesizing information from the web, one might imagine using LLMs to develop marketing or pricing strategies prior to the launch of a new product, and then iteratively querying LLMs over time to evaluate product-market fit and modify the marketing strategy.
		- > Hence, our approach to performing market research using GPT is to treat the model as a synthetic consumer rather than a source of knowledge.
	- Discussion Points (before solution)
	  collapsed:: true
		- > Product reviews, for example, which are likely present in the training set for GPT, may reveal something about customers’ **stated preferences** for products but may not always mention **prices** or other k**ey attributes of the product** or of the **decisionmaker** (e.g, income or demographics).
			- *"A large literature documents the differences between customer surveys, which elicit __stated preferences__ over bundles of goods, and __real-world demand data__, in which customer preferences are revealed by their __actual choices__."*
		- id:: 660adaa7-49e2-44ab-b254-2dcecf94446a
		  > If GPT can generate reasonable responses to each isolated question, will its responses across different questions be **internally consistent** in the ways we expect consumers to be? ((6601d330-7936-4411-a312-35e608c0beb1))
		- *"__posted comments__ about purchases are __neither a representative sample__ of actual sales data __nor prompted by typical consumer survey questions__."*
			- *GPT’s training set contains aspects of both: consumers comment online about actual or prospective purchases*
	- leave prompt engineering and optimization for future work.
- 🔸 {{g "Main direction"}}: Study the impact of **changes in the attributes** of goods on **choice probabilities** and **market shares**
  id:: 660ae529-91d9-4c45-8efd-3643bab517d7
- Discussion Points (actual)
  collapsed:: true
	- *"GPT is sensitive to the __phrasing of prompts__, and while many of the behaviors we show here are robust in direction, their magnitude can differ depending on the precise prompt we provide."*
	- *"We also found that, like human survey participants, GPT exhibits response __order bias__ and is much more likely to choose the first option in a binary choice than the second."*
- 🔹 Study Design
  collapsed:: true
	- Four studies.
	  collapsed:: true
		- each study...
			- series of prompts
			- varying key features
				- of the choice setting
				  collapsed:: true
					- *prices*
				- of customer attributes
				  collapsed:: true
					- *prior purchases*
					- *income*
	- Trivia
	  collapsed:: true
		- ((6601d330-7936-4411-a312-35e608c0beb1))
		  collapsed:: true
			- Market research concerns not only what customers will say about their preferences, but what their choices reveal about those underlying preferences when economic models are estimated using the resulting data. Analysis of the latter involves **subjecting humans to multiple questions** with **different contexts**, and requires humans to behave in ways that are, for the most part, **internally consistent**.
	- **Query GPT hundreds** of times
	  id:: 660ae597-6718-4a20-9d80-e06de3097602
	  collapsed:: true
		- ((660ae529-91d9-4c45-8efd-3643bab517d7))
		  collapsed:: true
			- which normally requires data from many randomly sampled customers or markets
		- ((6605ce4b-b28b-4001-a679-47c6565dccac))
			- Set the “temperature” on GPT to its maximum value for text completion (1.0)
	- 🔹 Proceed - ((65ff2f20-285f-4826-97e1-12a518530483))
	  collapsed:: true
		- prompt GPT to fill in the responses of a survey question
		  logseq.order-list-type:: number
			- as if it were a customer shopping in a category of interest
			- who was randomly selected to participate in a survey.
		- describe any relevant attributes of the customer
		  logseq.order-list-type:: number
			- (e.g., annual income),
		- offer one or two products for this customer to consider purchasing
		  logseq.order-list-type:: number
		- remind the customer that they can always choose not to make a purchase
		  logseq.order-list-type:: number
		- Ask GPT to fill in the response of this chosen customer by ending our prompt with “Customer:” 
		  logseq.order-list-type:: number
			- ((6605ce4a-9c73-4954-a461-611e8da7b3a8))
		- submit each of these prompts to GPT hundreds of times and aggregate the responses to construct our measures of interest
		  logseq.order-list-type:: number
		- logseq.order-list-type:: number
- Results
	- Preferences implied by GPT’s responses are **consistent with**
	  collapsed:: true
		- downward-sloping demand curves,
		  collapsed:: true
			- not monotonically downward-sloping - **feature**
			  collapsed:: true
				- ![](https://img001.prntscr.com/file/img001/6aQZ9zZKSE6LaK0P1yh9DQ.png)
				- much work in [[economics]] and [[marketing]] has documented several possible relevant factors, including context effects, [[preferences for round numbers]], [[prices as a signal of quality]], and [[left-digit effect]]s #pricing
			- Generally yes, but
				- *the decrease in demand __is quite small__ and seemingly unrepresentative of typical human consumers.*
				- **works better when comparing two products**
			- choice among multiple options
			  collapsed:: true
				- Graphs #.v-gallery-col2
					- ![](https://img001.prntscr.com/file/img001/kcW4TOV3S1WF0rDbIu6cgw.png)
					- ![](https://img001.prntscr.com/file/img001/lVlbAwFEQIu2_yVoIC_q7Q.png)
			- 🔸 Consistent with theory based on lower-higher priced items
				- Graphs #.v-gallery-col2
					- ![](https://img001.prntscr.com/file/img001/kcW4TOV3S1WF0rDbIu6cgw.png)
					- ![](https://img001.prntscr.com/file/img001/lVlbAwFEQIu2_yVoIC_q7Q.png)
		- Impact of income on demand
			- Aligns with general Economic theory
		- state dependence
			- serial correlation in customers’ choices
				- for example, In health insurance markets inertia drives patients to **repeatedly choose the same plan even when the plan’s attributes change significantly** (e.g., Handel, 2013; Pakes et al., 2021).
			- Aligns with the theory mentioned in papers. Self made data
		- diminishing marginal utility of wealth
	- Realism of GPT’s responses is similar to ones found in real surveys
		- [[Willingness-to-Pay (WTP)]]
		- Resulting [[WTP]] estimates seem realistic, both in magnitudes and in distribution.
		- a [conjoint]([[conjoint analysis]])-like approach to preference estimation yields results that are **strikingly similar** to those found in a recent survey of real consumers conducted by Fong et al. (2023).
			- ((660adf2c-b555-43eb-aa2d-8e0cf3a54f0f))
			  id:: 660ade81-8ab1-4588-856c-8c9e970421f2
		-
- Refs
  collapsed:: true
	- ((660ae25c-baa5-46d0-9547-33d00a1ef4c3))
		- Conceptually, the paper closest to ours is Netzer et al. (2012) who extract customer preferences from text.
	- ((660ae28c-e26a-4e02-a721-1c20ad247993))