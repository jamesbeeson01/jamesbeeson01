# James Beeson 🐝

Hello there! 👋

I am a data science student passionate about improving education, and using my research and data science skills to get there. I am also a lucky husband and proud father of a precious daughter.

- 🍎 I’m currently working on AI in Education research
- 🏫 I am a senior at Brigham Young University - Idaho
- 💻 I work in the BYUI faculty technology center, a place of technology innovation to help teachers and learners on campus

Languages:
- R (tidyverse)
- Python (pandas, OOP, ArcGIS)
- AutoLISP (AutoCAD Map 3D automation)

## Blog

### What I know Now About AI Impacts in Education
**7/16/2025**

So is AI hijacking our brains or making us geniuses? It depends...

Consider a classroom where the teacher gets up, stands in front of the students, and says nothing. After a moment of waiting, a student asks a question, and the teacher gives the answer clearly and directly. Then the silence continues until the next question. The teacher does not invite students to do homework. They do not ask the student what they think first. They do not respond in a way we think a teacher should. 

Learning is one of the most common uses of AI. Most of that time, that learning is in the form of asking AI a question and receiving an answer. That can be a great use case of AI, and people like it. That is why general use AI has been trained to act in this way. However, that can't be the only way someone learns, or even the primary way.

Students using general use AI are involved in a swiss army knife conversation. It can do everything but your dishes, including revising papers, writing an email, answering questions, giving life advice, being an emotional support block, and making its maker money. It would be nice to take that multitool and pull out the tutor tool, the best one for learning - but finding that tool within the AI is very unclear, and as of today it is not used by many users.

To be clear, the teacher does live inside general use AI, hiding and waiting. By far, its greatest advantage is personalized learning. Students can use AI within traditional frameworks, generating multiple choice quizzes and flashcards and inviting the AI to grade their answers ([Kasneci 2023](https://doi.org/10.1016/j.lindif.2023.102274)). They can ask the AI to help them think in new ways by asking curiosity-invoking questions ([Abdelghani et al., 2022](https://www.sciencedirect.com/science/article/pii/S1041608023000195?ref=pdf_download&fr=RR-2&rr=944885ffbbcadf03#bb0005)). It can evaluate the student's work, giving immediate feedback in real time - a task a teacher could never perform for every student in the class all at once. It has seemingly infinite time and attention for the student. But the AI's infinite eagerness has its costs for students. 

Research has been coming out showing the effects of AI use on learning, and the research is growing. One common trend is for people to become aware that they are beginning to think less for themselves, and offloading their thought processes to AI. This process has been termed "cognitive offloading" and has not only been a general perception in the population of AI users, but has also been studied empirically as a real issue ([Gerlich 2025](https://doi.org/10.3390/soc15010006)). Not everyone is losing their mind to AI, but a growing number of people literally are.

One theme in the literature to mitigate this risk of cognitive offloading is for users to demonstrate a certain set AI core competencies - things that will place them in a safe zone. These competencies are not yet widely agreed upon, but they may include ([Kasneci 2023](https://doi.org/10.1016/j.lindif.2023.102274); [Zu 2025](https://doi.org/10.1016/j.csi.2025.104006)):
1. Understanding the limitations of AI - usually by conscious experimentation
2. Allow the AI to think with them instead of in place of them
3. Use critical thinking and problem-solving skills to assess the AI
4. Verify AI's correctness with other more reliable materials
5. Generate perspectives and hypotheses, not answers

Having a student that is competent in using AI is the greatest protection for a student. 

### Creating a Agentic AI Tutor Chat
**7/16/2025**

Individuals have a responsibility to use AI wisely for learning, but wouldn't it be nice if the AI itself was a better tool for learning?

In an attempt both to explore the creation agentic AI and to see if I could make it into a better tutor, I programmed my own AI based on Google's Gemini and conducted an experiment to test it. The AI I designed has textbook content it is able to pull from, and with every prompt, makes an assessment of the user's learning stage in the instructional hierarchy. The experiment itself used this AI as a treatment, and another standard AI with the simple prompt "Hi! I'm a helpful tutor chat for your Education Psychology and Human Development class. What can I help you with?"

The volunteer sample size was too small to make any generalizable or statistical conclusions. However, from viewing their conversations, seeing their survey responses, and collecting their open ended feedback, my AI was no better than the simple prompt of the control group. The biggest advantage it had was 1) it had textbook content and was for that class alone, and 2) it was slow to answer questions (meaning it asked the student what they thought or what they knew before answering questions). Some people were frustrated by the second advantage, but upon viewing their conversations, I see that largely as a win (in most cases). However, in my opinion, there was a general consensus that the single prompt "I'm a helpful tutor" was better for learning than the usual ask anything mode.

My AI creation was a learning experience, albeit hardly conclusive as to how to control AI use. I intent to continue trying and learning to control AI. In the meantime, I agree with some of the literature which invites students to better understand AI and develop those core competencies of critical thinking, knowing AI's limitations, and putting in the work to think on their own with the AI as their assistant.

##### For coders: The technical side of creating the AI
The most interesting parts of making the AI, I think, were its use of a database for the textbook content, function calls with structured output, and guided thinking. With every user prompt, it would first ask if it needed to pull in textbook content for its response, then made an assessment of how it should respond based on the user's "learning stage" in the instructional hierarchy (which is an idea grounded in learning theory). 

I scraped the textbook content beforehand using [Firecrawl](firecrawl.dev). I had it generate a sitemap, then programmed in essence "for every url, scrape that content and put it as a database entry". I then looped through the content using Gemini to make of summary of the page and store the summary. When the function call was made to pull in textbook content, it was offered the page titles as enums it could respond with, and told in its description the content of each title in the form of 'title: summary \n title: summary'. This reduces the context needed to make a good decision and have relevant context for each response. 

The guided thinking was fairly simple. After pulling textbook content, it would receive a one-shot prompt with an example of how it could respond. I then had to concatenate to the end of the prompt "I will not comment on or mention this knowledge in my next response, but I will use it to inform how I respond." Otherwise, it would say things to the user that do not make sense. In essence, it gave a response to itself.

I found that this guided thinking, at least how I implemented it, was marginally helpful. The one-shot prompt I think invited it to respond with the same learning stage every time, which defeats its purpose. I also saw it ignore what it said it would do in the previous prompt to itself.

In some simpler cases, I found it to be extremely consistent, especially when using structured output like selecting textbook content given the same prompt. However, it is not consistent with my knowledge and reason.

Overall, I found that AI is hard to measure and difficult to wrangle. Even when I thought I could predict its behavior, it still acted in unexpected ways. I am still learning ways to make the AI more consistent with what I expect.

### Experimental Design is Complicated
**7/4/2025**

Science is easy. Pick a dependent variable (the thing to measure), the independent variable (treatment), randomize into a treatment and control group, and see what happens! Oh, but don't forget the bureaucracy.

#### Everything Surrounding Research

**People:** People research is particularly messy because it involves people. One way that people are different from objects is the fact that they have lives, experience joy and pain, and as such, there is an innate sense of morality in protecting other humans. That is why we have laws surrounding the protection of humans in social research. To get a study approved, it must go through the Institutional Review Board (IRB), who determines if you are giving the research participants enough information to make an informed decision, that any risks are no more than minimal, and that rewards outweigh negative effects. In preparing for an institutional review, I had to have my informed consent written out, justify the amount of information I would need to collect about people, and do all I can to protect and anonymize that information. I also had to provide my survey I used to measure "learning", which leads to something else surrounding research.

**Conceptualization:** It is difficult to measure concepts as abstract as "learning." It is one thing to measure whether or not they know some subject, but how do you measure something's potential to aid in learning? What does it mean to learn? If the goal is so nebulous as learning, it is not so easy to measure. The natural starting place for an academic is a literature review. This thorough consideration needs to be made before submitting an IRB. The trouble then becomes, how do we see observe something invisible, then how do I observe that thing. My resource limitations constrain me to grades and a survey.

**Instruments:** How do I get people to use my AI chat and take the survey? How do I make sure they use it correctly? How do I know if they used in incorrectly? How do I store the data? Answering these questions took the creation of a website with its own database, an integration with the survey, and communication with a class instructor to use an existing assignment for measurement. I had to design the website to assigned the user a treatment group in such a way that it led the user to do what they were supposed to without revealing what treatment group they were in. Just to run the experiment, user experience was a significant part of the process.

**More People:** People have to volunteer for the experiment, and people have to administer the experiment. In my case, the only significant funding needed was my time, which is fortunate. I did buy a domain for the website, but for something this small, it could be a fairly simple name. In order to get participants, I worked with an instructor to give students extra credit for participating. Still, there had to be announcements, assignment creation, and additional surveys to surround this accomodation (which can only move forward with help from the professor and TA's). In my case, this took a lot of waiting and coordination.

#### Where are we now?

Despite the hurdles, the experiment is now running. Only time will tell if it will yield any useful information. However, it feels nice to have a break in the waiting game.

### Web Dev is New: Building an AI Chat Bot Using AI
**6/14/2025**

I have a deep focus right now on questions of AI in education. What are some ways AI chat use can harm learning? What bounds should be placed on AI to mitigate these risks? How are students currently using AI to augment their education? What systems can we put in place to make an AI chat bot more supportive of quality, lasting learning. I decided I would answer these questions in 3 ways: 

1. Review academic literature and reading material on AI and the theory of learning.
2. View people's candid learning conversations with AI.
3. Try to influence learning by creating my own AI chat and assessing its efficacy (including human testing). 

In diving into the literature, I realized the learning curve I would face, having to mix qualitative and quantitative research while defining abstract ideas like "learning" or what good learning means. So far, I have learned that young adults and teenagers especially are starting to see themselves handing too much of their problem solving and decision making to AI, which has been coined as cognitive offloading. I have also seen a theme of needing to gain AI competencies. We need to understand what AI actually is if we want to use it well and keep it within its bounds. I will write more on those ideas later. For now, as I started to hit roadblocks, I decided to work on all three steps of the process at the same time. Now, I have reached a major milestone in the software development for stage 3.

In the age of vibe-coding, I thought I could not only use Gemini APIs to customize a chat but also pull together a website to use it, and I did! You can find the site here:
https://www.tutor-chat.space/

It is a chat bot used primarily for research, with its use disclaimers, survey, and the whole research gambit. Most importantly, it will allow me fine control around how the chat operates and allow me to view conversations linked to surveys to view a person's experience holistically. Right now, it just calls a standard version of Gemini, but it will do some very interesting things in the near future.

The biggest milestone and achievement for me is creating a website when I didn't know web dev. Now I know slightly more.

#### What I Learned

I went into creating this website with the following knowledge:
- The general structure of html and css
- html is structure, while css is design format
- I needed a backend, and
- I have used javascript lightly

While I used some YouTube tutorials (especially to learn what node.js was and how http communications work), the heavy lifting both for the website programming and teaching me about web development came from AI. It was able to give me specific answers to questions that get into the nitty gritty. I was able to ask questions as I saw how it coded, and was able to critize its code that helped me learn the important concepts.

In the process of vibe-coding website, I learned the following about the website programming and how frontend communicates with backend:
- javascript runs natively in the browser, which is its original purpose
- node.js is a runtime for javascript that lets it run outside a browser
- express is a useful library for simplifying a web app
- The difference between get and post requests is that post gives information before receiving
- How to fetch api calls (including my own server's apis), which use JSON and urls to communicate 
- Asynchronous functions are different than static functions in that they can be called at any time in any order
- JSON was modeled after javascript objects, but they are in fact different (I learned what a javascript object was)
- I still need frontend javascript even if I have backend javascript
- The frontend is handled by each person's computer, whereas the backend is one instance that serves everyone

I also found a learning curve in the process of publishing the website, which felt incredibly more complex than I expected. In the deployment process, I learned:
- I can't just click a button to deploy
- There are multiple ways to deploy a website
- Some methods try to put as much as possible into the frontend to minimize lag and backend usage
- Some websites opt for calling functions as a service instead of a traditional backend server
- Often databases are stored externally from the hosting service
- Some hosting offerings are stateless only
- Stateless means that the information from the session goes away on session end
- I need to get a separate domain name that routes to the ip address for my website
- In opting for a cloud virtual machine, I have to install git, node, and various other packages fresh
- I also have to get an SSL certificate for security (and the golden https status)
- How to store environment variables locally and in the VM

And I am sure there are more. I did not even touch on using the Gemini API, which I have yet to dive deeply into. 

#### On Vibe-Coding

I was amazed at how much agent mode with Claude was able to do for me. I started by simply saying something like "give me a basic express node web app that mimics an AI chat like ChatGPT." Out of the gate it created a nice shell that I could iterate with. I found that learning beforehand what node.js was and the principles of how websites communicate, it was much easier to critize when the AI was doing something stupid and I could correct it. Having other programming background also helped me have a language to communicate with the AI and let it know what I want changed. AI was invaluable when it came to publishing the website because it had enough complexities and custom scenarios that are hard to navigate with typical tutorials. I was able to get advice on which method to use for my hosting needs, and it helped me identify any holes in my knowledge that were stopping me from getting it published.

#### Wrap-Up

Here is that link again: 
https://www.tutor-chat.space/

Right now, it is a relief to have something that people can see and touch (metaphorically). There is more to do, though. 

Back to the research! And playing with Gemini...
