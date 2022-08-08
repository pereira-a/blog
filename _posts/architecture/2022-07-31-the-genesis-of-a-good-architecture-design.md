---
title: "The genesis of (a good) architecture design"
categories:
  - architecture
tags:
  - architecture
  - opinion
toc: true
toc_label: "Table of Contents"
toc_icon: "fas fa-bars"
---

When you hear me insisting that architecture design is an important (if not the most important) phase of software design, I bet you think “Of course it is, there’s nothing new to me here”. I have no doubt in fact that most of us believe this, but do we know how to do it? And most notably, do we know how to do it well?

Our industry is a young one. We have only been creating programs that run on what we recognise as computers for around 70 years. Therefore, we are constantly looking at other professions in an attempt to explain what we do. We borrow names from professions that are based on a body of knowledge going back thousands of years, like engineers or architects, which implies that we know what we are doing when often we plainly don’t.

When we borrow a name like **‘architect’** to prop up our industry, we also seek to copy methods from that profession: the **idea of someone who draws a detailed plan for others to interpret and expects it to be followed; a balance between artist and engineer, overseeing the creation of what is normally a singular vision**. In our industry, this view leads to some terrible practices that result in building a view to inform the construction of a ‘perfect’ system, without taking the fundamentally unknowable future into account.

For the sake of real architects, we can agree that the term doesn’t actually accurately describe our work. Unfortunately, we are stuck with it for now. So, the best we can do is to **redefine what it means in our context**.

![Architecture hell](https://miro.medium.com/max/1080/0*61U3JNHmAud_bhq9)

# The Unpredictability of the Future

> Let he who has never had a project whose requirements changed after the start of implementation cast the first stone. 

I surely believe you didn’t smash the screen with a rock because participating in a project where this happens is such a rare case (or, less likely, maybe because you don’t have a random rock at your disposal). **We work in a fierce environment, and our requirements shift more rapidly than do those for people who design and erect buildings** (as do the tools and techniques at our disposal).

We have to accept that once our software gets into the hands of our customers (sometimes even before that) <mark> we will have to react and adapt, rather than it being a never-changing artefact</mark>. Our mentality needs to shift away from creating the perfect end product, and instead **focus on creating a framework in which the right systems can emerge and continue to grow**. Every detail of the future cannot be predicted, and so rather than plan for any eventuality, we should plan to allow for change by avoiding the urge to over-specify everything.

![Wise yoda](https://i.giphy.com/media/3ornk3ifPpyCwE8Ti8/giphy.webp)

# The Coding Architect 

One thing that people often forget is that our systems don’t just accommodate users. They also accommodate the development and operations teams who work with them too. It’s needless to say that the happiness of these teams directly affects the quality of the end product, so **architects have a duty to ensure that the system is ‘habitable’ for developers as well**.

To ensure that systems are friendly to developers, **we need to understand how design decisions impact on their work**. The best way to gain this knowledge is to work closely with the teams and inherit their pains, by rolling up our sleeves and getting some coding done — even if it’s just for a short period of time. This is significantly more effective than making a call or just looking at the code.

I cannot emphasise how strongly I believe in the importance of an <mark> architect working united with the team</mark>. I’ll summarise some of the problems that can arise as a consequence of a non-coding architect mindset versus the benefits of the opposite mindset.

![Coding cat](https://miro.medium.com/max/300/0*F8XA7lvBTPvdG3ME)

Watching a project from a high-level perspective, we can construct an inaccurate perception of its actual state. The timeline looks good. Work is being done. Functionality is being added. But is the technical view being accomplished? And what about team motivation? What else is going on?

- **Architects lose touch with tools and technologies:** we can sum this up as ‘unless the architect follows his own recommendations, he could be completely unaware of the repercussions of his choices’. Also, working with the development team (instead of staying locked in his own bubble) is an excellent opportunity to acknowledge new and more sophisticated technologies.
- **Technical view not accomplished:** coding side-by-side with the team is a nice way of ensuring by example that the planned technical view is followed. Also, it’s a better way to guarantee the code doesn’t stray from the vision before it’s too late to handle the technical debt.
- **Design doesn’t fit changing requirements:** we already know that we can’t assume a static world for our projects; architecture and design often require change. Being closer to the team, an architect can easily forecast changes to come and react rapidly by working in collaboration with the team to evolve the architecture of the system.
- **Developers become frustrated:** being close to the team is important to an architect to ensure that he understands their needs and pains. If the architectural plan causes problems or deviates from client requirements, it’s better to work closely with the team, avoiding delays in communication.

By working in collaboration and staying close to the team, the above problems can be easily avoided. If that isn’t enough for you, the following benefits can also be achieved:

- **A better understanding of the design:** when architects write code, they have the opportunity to communicate design ideas and principles to developers with greater impact. The creation of prototypes it’s also a viable option to demonstrate how architectural designs are implemented in real life.
- **Real-time design updates:** architects who code can evaluate alternatives in real time. Keeping an architect within the team ensures the architecture can pivot to fulfill changing needs. Additionally, there’s less of a push to over-architect everything upfront.

The following comic show the misconception about being an architect.
![Dilbert comic](https://miro.medium.com/max/700/0*ddKajnM4cO5ZjSIs.gif)

# All Rowing in the Same Direction

Every company has high-level goals defined at a global or division level, which may not include technology at all: **strategic goals**. These goals have the objective of setting the direction **in which the organisation is heading**, and so the technology needs to be aligned with them.

The software architect has an important role in guaranteeing that we all are rowing in the same direction, to achieve common goals. So, he needs to map the strategic goals into a technical view, and this may mean that some trade-offs must be considered. To do this job the software architect must **define a set of principles and practices to guide development**.

Principles are rules to **align the technical view with some larger goals**, and will sometimes change. For example, if one of the company’s strategic goals is to decrease the time to market for new features, you may define a principle that says that delivery teams have full control over the lifecycle of their software to ship whenever they are ready, independently of any other team.

**Practices are how we ensure the principles are being carried out**. They are a set of detailed, practical guides for performing tasks. They will often be **technology-specific and should be low level enough that any developer can understand them**. Practices can include coding guidelines, that all log data needs to be captured centrally, or that HTTP/REST is the standard integration style. As with principles, sometimes practices reflect obstacles for your organisation. For example, if you only support CentOS, this will need to be reflected in your practices.

![All rowing in the same direction](https://miro.medium.com/max/480/0*hmo9tpg-CsBzalsI)

# Your Job Is Not Done

After the project’s development start, **the architect is not supposed to disappear into thin air to only become a ghost of the past**. If one of the architect’s jobs is ensuring there is a technical vision, then governance is about ensuring what we are building matches this vision, and evolving the vision is needed.

> Governance ensures that enterprise objectives are achieved by evaluating stakeholder needs, conditions and options; setting direction through prioritization and decision making; and monitoring performance, compliance, and progress against agreed-on direction and objectives - <cite><a href="https://www.oo2.fr/sites/default/files/document/pdf/cobit-5_res_eng_1012.pdf">COBIT 5</a></cite>

Architects are responsible for many things. They need to ensure there is a **set of principles that guide development**, and that these principles match the organisation’s strategy. They also need to make sure th**at these principles don’t require working practices that make developers miserable**. They need to **keep up to date with new technology** and know when to make the right trade-offs. All this, and they also need to carry people with them, to **ensure that the colleagues they are working with understand the decisions being made and are brought in to carry them out**. Oh, and we’ve already talked about this: they need to **spend some time with the teams** to understand the impact of their decisions.

All this as well as asking an architect to also work on governance is a tall order, right? Well yes, but it is also essential, and it doesn’t mean it’s a job to do alone. Normally, governance is a group activity. It could be an informal chat or a more structured regular meeting with a good representation of the entire team.

![Architect disappears](https://miro.medium.com/max/500/0*6xHJmtY4gICuV2CP.jpg)

# Summary

You are probably asking yourself why I spent all this time talking about architects when the title suggests I was going to talk about architecture design. The answer is as obvious as the question: **good architecture begins with the architect**. Defining some core attributes of software architects defines, by consequence, core attributes for architecture design itself (as you may have spotted already). And of course, there’s plenty more to say about architecture, but we couldn’t skip the this because good architectures won’t serve the greater good if not well applied and designed with the right mindset.

We said that the architects in our industry are not the same as the architects of buildings, as we sometimes believe. So, we’ve tried to redefine what it means to be an architect in our context. And so to finish, I’ll summarise what we identified in this blog post as the core attributes of a software architect:

- **Vision:** ensure there is a clearly communicated technical vision for the system that will help it meet the customer’s and organisation’s requirements.
- **Empathy:** understand the impact of decisions on customers and colleagues.
- **Collaboration:** engage with as many peers and colleagues as possible to help define, refine and execute the vision.
- **Adaptability:** make sure that the technical vision changes whenever the customers or the organisation require it.
- **Governance:** ensure that the system being implemented fits the technical vision.