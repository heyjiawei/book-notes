## 37 things one architect knows about IT Transformation: A Chief Architect's Journey

### The roles and qualitiesof an architect in a large enterprise
1. What does an entreprise architect do?
- The definition of Architect is to design buildings and supervise construction. For enterprise architects, they need to design and supervise how software created by ground floor engineers solve the needs of those at higher floors. 
- They need to master 3 areas - Impact, Leadership and Skill.
  - This means that they should have the soft skills (and political skills) needed to navigate top management. To Be able to show how a project can benefit the company. 
  - Leadership skills to supervise ground floor engineers and nature younger, upcoming architects.
  - And last but not least, technical skills to design software and make good technical decisions. 
- While they can solve production fires, that should not be their main job. Nor should that be a criteria of how good an architect is. Recall the definition of an Architect.

2. Why does corporate IT make bad IT decisions?
- The fact is, we are all bad decision makers. 
- We are unconsciously biased to easier choices. This is because thinking fast requires little cognitive load as compared to slow, conscious pondering
- This unconscious bias is pointed out on 'The law of small numbers' (Kahneman, Daniel: Thinking, Fast and Slow, Farrar, Straus and Giroux). This law states that we humans have a tendency to jump to conclusions based on sample sizes that are too small to be significant.
  - A fallacy that exemplifies this would be choosing not to update to the latest libraries because it could cause production issues. In this case, the risk of continuing with the current library version was not considered and this decision could be more risky. The library could have patched a serious security flaw, or the updates could snowball, which would increase the difficulty of updating in the library in future.
- We can remove confirmation bias in our decision with metrics, models and experiments that are designed to overcome confirmation bias. 
- We can also try to avoid making irreversible decisions - by eliminating the need to make irreversible decisions in the first place, or making decisions that can be changed easily in the future.

3. What should we do when a project or application goes sour?
- We must question and get to the bottom of the matter. The 5 Whys and 1 How is a good method to begin with. These questions help to reveal gaps or misalignment in knowledge. As well as the decisions and assumptions made.
  - A solution to this is to conduct architectural review. Hopefully with architectural reviews, these assumptions will be pointed out and documented so future batches won't repeat the same mistakes.
  - If the above solution is not working out, for example, the documents are not up to expectations, one has to step in and define these documentation expectations. Set up workshops to educate all on how they should create high standard architectural documentations rather than a setting up a documentation review meeting at the end of planning cycles. The former requires good writing skills and sufficient helpers while the latter would eat up everyone's time and could potentially drag the development cycle longer.
  
### How to think about architecture at enterprise scale
Gregor observes his surroundings to see how it can applied to architecture. How and why does a coffee chain like Starbucks handle the following:
  1. Exception Handling - when the barista serves up the wrong order what does he/she do? When the client can't pay, what should the barista do?
  - They can choose to ignore the order by discarding all work done thus far. One should also consider if the trade-off, correcting the error, is more expensive than just letting things be.
  - The barista can re-attempt the order again, assuming that in their next attempt, they will succeed.
  - The barista can compensate with another item on the menu
  - When encountering a failure in a transaction, it is best if all steps are idempotent - meaning that they can receive the same command multiple times but always produce the same results.
  2. Back pressure - when there are many customers who have already placed an order are waiting in line
  3. Why does Starbucks use a different set of terminologies (e.g. venti, tall etc.)
  - By using a different set of terminologies, they can establish a Canonical Data Model that removes uncertainties and this can help optimize downstream processing.

1. Document decisions
  - Architectural documents should include non-trivial decisions (or essence of the decision) and the rationale behind them. 
  - If diagrams are used to describe the architecture of components, they should be drawn with a universal language (like UML) so that everyone can understand what the diagram means. These diagrams should not require a meeting to explain the diagram, or require users to constantly refer to a legend. 
  - Code should not be the only documentation of what an application does. What is interesting or how a software is built in a certain way needs to be point out. The code level is merely trees. It does not allow us to see the forest with ease.
  
2. Think in systems
  - Systems thinking focuses on systems behaviour- how does the system's components influence each other and cause the system to behave a certain way. It is concerned with understanding the inter-related behaviour between systems. In contrast, control system theory describes the system behaviour and focus on 'core components'

E.g. A heater in control system theory view point, is the element that heats up the room. If the room gets too cold, we turn up the heat. Whereas in system thinking, we reason how variables can affect the system. The room could get colder due to the frequent opening of the door. Warm air escapes the room when the door opens and hence, if we keep the door closed, we can main the room's warm temperature.
  - System thinking can rely on feedback loops to identify the variables influencing systems.
    - Negative feedback loops aim to keep the system in a stable state. A change in one variable will be countered by another to bring the system back to a stable state. Large legacy systems usually have this loop, making it difficult to move away from them.
    - Positive feedback loops cause a spiraling effect. A single variable change can cause a series of chain reaction and make the system unmanageable. An example of this is the rich getting richer. Offsetting a spiraling effect resulting from a positive feedback loop is hard.
  - Systems thinking can be applied to both application and organisation. **If you want to change its behaviour, change its system**

3. Trade-offs of using vendors applications over developing applications in-house
- Using vendors applications or purchasing customised applications from vendors can save time and effort. They can be costly in the long run, when you are locked-in to their products. They can be time-consuming when you troubleshoot a bug. And lastly, the system architecture and skills will be passed on to them, instead of the organisation. This will make it difficult to bring the applications back 'in-house'.

4. Killing old systems and constantly upgrading versions
- The saying of 'if it is still running, don't fix it' shouldn't be followed blindly. This causes legacy applications to rot further. 
- Instead of paying for extended vendor support, take the pain of upgrading versions, changing of upgrading dependencies frequently. This needs to be ingrained in the company culture.
- The is a distinction between operation (aka. run) and development (aka. change). Operation keeps the software running and could include hardware. Operation focuses on delivering software. When we separate engineers into these 2 categories, it can impede changes. It is the running and supporting of legacy systems that increase IT cost, not the cost of change.

5. Let the machines do the mundane work.
- We should automate when it is possible, and make it self-service at the very least. If can bring the following benefits:
  - Reduce human errors. This is a huge factor as we can never remove human-errors.
  - Increase confidence in delivering a product to the market
  - Most importantly, it isn't just about the trade-off with efficiency. It is also a strategy in reducing disasters and releasing human resource to problems machines can't solve.
  
6. Architects should come up with their own technical map. What products to use for which areas, which products are compatible with their systems and their strategy for using certain products.
  
### How tocommunicate to a variety of stakeholders
Architects need to close the gap between technical knowledge and high-level business decision makers. They need to clearly communicate the trade-offs of technical decisions on business. 

This is a vague checklist of how one should communicate in their documentation or presentations:
- Provide a mental model for your audience
- When defining terms, define them in the context of your problem
- Skip details that will not cause a large gap between your audience's understanding
- Create a common language so they can easily understand what you are talking about
- Don't try to skittle around issues
- Don't be lengthy. People have short attention span
- Prefer words over speaking. People read faster than they can listen
- Make your documents searchable and versioned.
- Story-telling headers as compared to 'introduction' are more meaningful
- Diagrams provide good visual representation. Use them strategically
- Use Callouts to indicate additional details that can be skipped without losing the train of thought.
- Test your audience intermittently to see if they understood your point
- Using examples and metaphors will usually give the audience the same, clear message as compared to statements, which may be interpreted differently.  

Show them demos to get their attention. This will increase their chances of to listening to you. Show them the results and how they are relevant.

### Organisational structures and how they can fail
1. Control is an illusion
- Most organisations are structured like a pyramid. This means news from the bottom will pass through many layers before they reach the top. Control is an illusion because status reports from the bottom may not reflect reality as they may choose not to report the bad stuff. 
- This discrepancy between reality and perceived reality is due to slow feedback loops, or choosing to ignore feedback loops. Organisations that run with command-and-control structures would often fall into this trap.
- Instead of relying on active discipline - demanding blind execution, mitigate this with passive obedience - let the people at the bottom do what is deem appropriate, adjust to the unforeseen circumstances without having to report back. This can be applied in production issues. Rather than asking for status reports every hourly interval when a production issue occurs, leave the team to fix the production issue and have them report back when they are done.

To obtain actual control, you will need 3 elements:
- Enablement - let people do what they need to do first
- Autonomy - let people figure out how they can achieve their goals. Done at their level, it would have the shortest feedback cycle
- Timeline - set specific goals and provide reasonable timeline for them to achieve

2. The bad habit of building from bottom up
- When many applications are built, they may have many reusable components. Rather than building these reusable components first, build only what you need first. Refactor common components later.

3. Having black markets within
- Black markets here refer to shortcuts people take to get what they need because doing things by the proper route is too tedious or inefficient. 
- These black markets are inefficient as they are undocumented and based on unwritten rules. They require new-comers to learn the black market system from another colleague, which will take time and time spent on this can cost the organisation. Additionally, these knowledge will not be retained. They are lost when an employee closely connected to the black market leaves the company. They also break feedback cycles, which contributes to a false sense of security. Black markets cannot be out-sourced. Hence, the cost of black markets are difficult to measure.
- Black markets can be shut down by building a more efficient system that enables progress. This can be done by automation or self-service portals and reducing the number of steps to get to people to goals. If your company already has these in-placed and is still facing a black market, you should question if the portals are user-friendly and spend time digging into why people are not using these processes. By shutting down black markets, the organisation can observe real behaviour and make better decisions. But to make that happen, they must first be willing to pay upfront to improving processes.

4.  Not thinking in terms of scale
A large organisation needs to think about scalability. Here are common mistakes:
  - Too many meetings because of the need to get everyone on the same page. This can be reduced by providing status update to everyone before the meeting, be it in emails or chats, and provide them an option to skip the meeting. After all, if someone is in a meeting, they can't get work done.
  - Emails flooding everyone's inbox with to and fro responses and increasing storage space needed to store them. Instead, integrate chat with email. Use chats to continue real-time discussions or urgent responses when needed and emails to start or close off status.
  - Too many repeated questions. Instead of answering to one person, build a cache/repository/web portal that contain all these FAQ. 
  - Reduce alignment meetings. They are meetings with no clear objectives. At the least, only include direct participants and make it self-service for the rest.
  
5. Implementing agile wrongly

Agile is not:
  - Just about moving fast
  - trying to predict the environment and eliminating uncertainty
  
Agile is:
  - embracing the frequent change request in software development cycles
  
- Agile needs iron discipline and a lot of practice. An example of agile at work is the pit-stop guys at work in F1 race.
- Agile works best in an environment that has solid deployment, testing tools and processes in place. It is not for everyone. Mimicking a portion of agile process does not make you run in 'agile'. Instead, it could be chaos in disguise.
- Choosing to remain slow can increase the underlying chaos in your organisation. 
- Gregor observes that result-oriented objectives can cause a lack of discipline. It would get things done - by going around issues or closing a blind eye when issues pop up. Instead, set output-oriented objectives. Output-oriented objectives are process based goals as compared to result-oriented objectives (outcome based goals). The former would require discipline to achieve its objectives.

### How to transform traditional organisations
1. Without pain, it is hard to change
  - Gregor summarised change into 3 stages, the wake up call, overcoming the illusion that change is easy, and lastly, setting up habits and processes to help ease your journey to your goals. Every stage is exponentially harder to get to and stay on. But the results are worth it
  - Complacency is the enemy of change. When you think that things are not that bad, you lose motivation to change.
  - A solution for organistions to change is to create near-death experience to get people onto the next stage. But done too many times, it would have the opposite effect.
  - Progress at the initial stage is hard and slow. You would need to transparent to upper management well, and back it up with demonstrations to ease their mind.
  - When your change program is successful, make sure your team or department does not stray too far from the company. To far will make re-integration difficult. Too far, people will leave. The grass always looks greener on the other side.
   - All in all, you have to be tactful when you push change. Do it slowly
   
 2. Start embracing economies of speed ather than economies of scale.
 - Size can be an advantage but it makes an organisation slow. The slowness comes from the overhead of processes to be efficient. Economies of scale is overly simplistic as it ignores the cost of intermediate products or processes.
 - Focusing on economies of scale can change an organisation values - to prioritise resource efficiency over customer efficiency.
 - In a static environment, being large is good. In an environment of rapid change, economies of speed wins.
 - Don't focus merely on optimizing a step (processing efficiency), optimize the flow as well (flow efficiency)
 - Don't estimate the value of speed. The missed opportunities from delays can be much higher than the cost of development.
 - The cost of valuing predictability
  - All projects in a corporate setting normally have estimates. Being pressured to keep to a timeline so as to manage things easier could cause the adverse effect: sandbagging.
  - Sandbagging is the repeated overestimate of timeline so as to avoid criticism and avoid budget estimates cut.
 - Switch to economies of speed by accepting that it could be less efficient. Usually, this change comes when IT drives business opportunities instead of being a cost center.
 
 3. Increase and maintain feedback loops
 - Reduce feedback time by forming teams that span the vertical hierarchy.
   - They should carry full responsibility from conceptualization to operations and refinement so as to form a 'you build it, you run it' attitude.
   - Remove unnecessary synchronization points and have all decisions made within the project team.
 - The challenge this is that it requires qualified staff, a compact team (preferably not more than 16), a willingness to collaborate across skill set and a low friction environment.
 
 4. Challenges getting to 'there'
  - Beware of highest paid person opinion.
  - Understand that innovation takes time. Disruptive technology may not beat existing / matured engines at its infancy stage, but when they surpass, they can threaten the company that didn't invest early.
  - Change the mindset that required skill can be brought at will. It can't. Whatever you outsource, it is an opportunity cost and knowledge lost.
  - Lastly, keep in mind that the digital reality may not be what you expect in the end. Some roles may be redefined and make some people unhappy. This can come in terms of steeper learning curves, more complexity, etc. Change is not about making people happy. It is about survival.
    
    
