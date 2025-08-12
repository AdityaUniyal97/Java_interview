Artificial Intelligence is a branch of computer science that focuses on creating a machine thath can perform tasks that typically required human intelligence.These tasks include problem solving , learning reasoning etc.
**Key Aspect of AI**
1) **Machine Lerning :** AI system learns from the data and improve thier perfromance with the time.
2) **Natural Language Processing(NLP) :** AI enables the machine to understand and process human language
3) **Computer Vision :** Ai analyzed visual data from the world.
4) **Robotics :** Ai-powered robots perfrom complex task in industries like healthcare , manufacturing etc
**Goals of AI** 
  1) Develop systems that can think , learn and adapt like humans
  2) Automate the repeatative and complex task
  3) Improve efficency and accuracy in various fields 

## Foundations and History of AI
**Foundation of AI**
AI is based on multiple disciplinese including :=>
**1) Mathmetics :** Provide concepts like logic , problality and algorithm for AI development
**2) Computer Scinece :** Helps in Programming , Data-structures etc
**3) Cognitive Science :** Studies human thinking process to develop intelligent systems.
**4) Neuoscience :** Helps to design neural network inspired by human brain

**History of AI**
**1) 1940s-1950s :** Alan turing introduces the idea of machine simulating human intelligence.The Turing test is proposed to check if a machine can exhibit human - like response or not.
**2) 1956(Birth of AI) :** THe term Aritifical Intelligence was coined at the Dartmouth Conference . Early AI systems were focused on solving problems and symbolic reasoning.
**3) 1960-1970 :** AI researcher exapnded it into expert systems and logic based reasoning. Arrising issues led to an "AI Winter" due to slow progrerss
**4) 1980-1990 :** Development of expert system that can mimic human decsion - making . AI saw improvememnt with machine learning algorithm and neural networks.
**5) 2000 - present :** Growth of Deep learning , Big Data and Ai Applications in health care and finance

## Applications of AI
AI is used in varius fileds to improve efficiency , automate tasks and solve complex problems.
**1) HealthCare :**
-  AI - Powered diagnostice system help detect diseases like cancer.
- Robotic surgery assists the doctor in precise surgery
**2) Education :**
- Personalized Learning - adaptive content based upon the student performance
- ChatBot - help the student with thier doubts and course related querries
**3) Bussiness and Finance :** 
- AI is used for fraud detection in banking and online transactions.
- Stock market predications are made using AI - based data analysis.
**4) Transportation :**
- AI enables self driving cars like tesla
- AI is used in traffic management system to reduce the congestion
- Navigation apps like Google map use AI for route optimization

## Intelligent Agents
An Intelligent Agent is a system(a software program or a machine) that observes  , thinks  and takes the action to achieve the goal
For example :=>
- A self driving car senses the road , decides the best route and drive safely.
- SIRI or Google Assistant: listen your voice , process it and than respond to it.`
**Features of Intelligent Agents:**
- Autonomus: works on its own without human help.
- Observes : use sensors and cameras to understand the environment. 
- Learns :  Improve thier performance with expierence
- Goal-Orientation: Work towards a goal efficently. 
# *Types of Intelligent Agents:*
Intelligent agents can be classified into five types based upon how they act to thier environment.
**1) Simple Reflex Agent :** 
- Acts based upon the predefined rules without considering past expirences
- Works on the principle of : 
            condtion -> take this action
- Example = Traffic light change thier color without analyzing the traffic flow.
**2) Model-Based Reflex Agent :**
- Maintains a internal model of the environment to make better decisions 
- Can remember past situations to improve repsonses
- Example =  A self diving car store the information about the road and traffic signols for better navigations 
**3) Goal Based Agent :**
- Takes the action to achieve goal , rather than just reacting to it.
- Uses the search and decision making teachniques to choose the best action.
- Example = A chess Ai calculates the best possile move to defeat an opponent
**4) Utility-Based Agent :** 
- Selects the actions based upon how benficial they are by using utility function(is a way to measure the success rate).
- It maximises the efficiency and provide the best possible outcome.
- Example = Google Map finds the fastest route by analyzing the real time traffic data.
**5) Learning Agent :** 
- Learn from the expirence and improve itself with the time.
- Uses the techniques like Machine larning algorithms to make better decisions.
- Example : YouTube recommendation system 

## **Structure of Intelligent Agents**
An Intelligent Agent is a system(a software program or a machine) that observes  , thinks  and takes the action to achieve the goal It has different parts that helps to work together.
**1.Archchitecture(Body of the Agent)**
- This the hardware or platform on which the agent runs.
- Example: A robot, a self-driving,or a voice assistant
**2.AgentProgram(Brain of the Agent)**
- This is the software that decides what action to take based upon the input provided
- Example: The Ai in a self driving car decides when to stop or turn
**3.Sensors** 
- Sensors collects the information from the environment
- Example: Cameras and radars = in a self driving car
- Microphones in alexa and google assisntant
**4.Actuators(Hands and Legs of the Agent)**
- Actuator perfroms the actions based on the decision
- Example: Wheels and Sterring in a self driving car
- Speaker in a voice assistant that reponds to your request
**5.Decision-Making(Thinking Process)**
- The agent analyzes the input and chooses the best action.
- Example: A chatbot understand the question and give correct reply
**6.Learning**
- Some agents learn from expirence and improve over time
- Example YouTube recommendation system.

## Computer Vision
Computer vision is a filed of articficial intelligence thaht allow the computer to see , understand and process the image , video like human. It helps the machine to recognize the object , faces and scenes from the visual data.
**How Computer Vision Works**
1. *Image Acquisition =* The computer captures the image or video using cameras or sensors
2. *Preprocessing =* The image is cleaned and enhanced for better understanding
3. *Feature Extraction =* Important details like edges,colors and shapes are identified
4. *Analysis and Recognization =* Ai process the data and recognizes object , faces or actions
5. *Decision Making =* Based upon the analysis the system perform the task.
**Applications of Computer Vision**
- *Face Recogization :* Used in unlocking phone using the face id
- *Object Detection :* Helps the self driving car to identify the pedestrian , traffic light and obstacle

## NLP(Natural Language Processing)
NLP is a branch of a Artificial Inteliigence thaht helps the computer to understand , and genrate human language response(in written or in spoken). 
**How NLP Works**
- The System Recives the  input in text or voice fom the user
- Now the AI will start understnding the input by breaking down all the words 
- After undeerstanding the AI generate the meaning full output
**Applications of NLP**
- ChatBot & Voice Assistant = Google Assistant , ALexa , siri
- Google Search = NLP helps google to understand and show the best result
- Language Translator = google understand and translate one language to ansother

# **Unit = 02**
## UnInformed Search(Blind Search):
Uninfromed Search is the search where the AI doesnt have any extra information about the target . It just blindly move to all the path until it finds the target
![[Pasted image 20250319162628.png]]
**Types of uninformed Search:**
*1. Breadth First Search(BFS):* 
- Explores all the neighbouring nodes or the adjacent nodes of a root node
- BFS uses the Queue(which follows the FIFO = First in First Out) DS to keep the track of nodes
 EXECUTION OF BFS :
 1- Start A , mark it visited , Queue[A]
 2- Deque A , add the adajcent nodes B,C to Queue[B,C]
 3- Deque B , add the adjacent nodes D,E to Queue[C,D,E]
 4- Deque C , add the adjacent nodes F,G to Queue[D,E,F,G]
 5- Deque D , No unmarked Node , Queue[E,F,G]
 6- Deque E  , No unmarked Node , Queue[F,G]
 7- Deque F  , No unmarked Node , Queue[G]
 8- Deque G , No unmarked Node , Queue[]
 ANSWERE = A->B->C->D->E->F->G

*2.Depth first Searcch(DFS):*
- DFS explore one path deeply before backtracking on it.
- It uses the Stack(which follows the LIFO = Last in First Out) DS to keep the track of Nodes
EXECUTION OF DFS :
1- Start A , mark it visitied , Stack[A]
2- Pop A , add the adjacent B , Stack[B]
3- Pop B , add the adajcent D , Stack[D]
4- Pop D , No Unmarked Node , Stack[]
5- BackTracking to B , add another adjacent  E , Stack[E]
6- Pop E , No Unmarked Node , Stack[]
7- Backtracking to A , add another adjacent C , Stack[C]
8- Pop C , add the adajcent F , Stack[F]
9- Pop F , No Unmarked Node 
10- Backtracking to C , add another adjacent G , Stack[G]
11- Pop G , No Unmarked Node
ANSWERE = A->B->D->E->C->F->G

## Informed Search
Informed Search is a method where the AI uses the extra information called as the heuristic to find the best path instead of blindly searching
- It uses the heuristic function yo estimate the best direction
- Instead of looking all the path like the uninformed search it give priorty to the best looking option
- Faster as comparison to the uninformed search
- Efficient because it requires less operations
- Uses less memory 
- Ex: Best FIrst Search,

## Uninformed Search
Uninformed Search is a method where the AI blindly travells all the nodes till reach the target
- Explore all the possible path blindly until it finds the target
- Search for solution without any extra infromation about it
- Slower because it checks all the nodes
- Less Efficeinet 
- Required more memory
- Ex: BFS , DFS

## **Local Search**
Local search is a teachnique which is used to find the best solution by exploring nearby solution instead of checking all possible ones . ok
## Hill Climbing
Hill climbing is an algorithm thaht tries to find the best solution by making small changes and always moving towards better result. It stops when no more improvement is possible
**Working**
1. Start from initial point
2. Check nearby node and move toward the one that gives best result
3. Repeat the process until no better soltuion is found
**Problem**
- Local Maxima = get stuck in the peak that is not high overall
- Plateau = a flat area where no nearby solutions are same
- Ridge  = a narrow path leading to best solution but the algorithm struggles to follow it






# Unit 3
## **Supervised**
Here the model learn from the labeled data(input with its correct output) . It  finds the realtion between the input and the output) . The goal is to make predictions based upon the labeleed data . Used in classifications such as Email Spam classifier and Stock Price Pridictions
**Algorithm:** 
- Linear Regression
- Decision Tree
- Logistic Regression

# **Unsupervised**
Here the Model is given unlabeeled data(only inputs and no outputs) . The goal is to  find the hidden patterns or grouping the data. Used for clustering 
**Algorithm:**
- K-means clustering
- Hierarchical clustering

# **Decision Tree**
A tree like model that makes the decision based  on the input features. Used for both classification and regression.
*Example:*
**Classification** : Should i play the tennis ? (Yes / No based on wheather , humidity)
**Regression:*** Predicting house price based upon the features(rooms , locations)

*Componenets:*
1. **Root Node** Top most decision point(eg Is it Sunny ?)
2. **Branches** Outcome of a decision(eg if yes -> go left , else -> go right)
3. **Leaf Node** Final predications(eg Play tennis: Yes)

*How Decision Tree Learn*
- **Recursive Partitioning** Split data into homogenous(pure) subset where the majority of the samples in a node belongs to the same class
- **Splitting Criteria** : 
   - **Classification** : Uses Gini Index : Measure impurity in the data
   - **Entropy**: Meausre the disorder entropy
   - **Information Gain** :  Meausre how much entropy is reduced after splitting

**Avoiding Overftting** Overfitting can be reduced by two methods
- **Pruning** Here we remove the nodes that dont improve the accuracy
  - **pre-pruning** Remove nodes that dont improve validation accuracy
- **Validation Set** Moitor accuracy to decide prune 

# Statistical learning Model
Is a part of a machine learning that uses the Mathametics and statistical techniques to make predications from data. Goal is to find the relationship between the input and the output
**Types of Statistical Learning Model**

- **Parmetric Models**  = Here the model have the fixed structure(eg Linear Equation) . Model can learn easily with few parameters 
  Example:
- Linear Regression -> for predicating the numbers
- Logistic Regresion -> For classification
- Naive byes -> uses probality
 *Advantage* : Simple and easy to understand and implement , fast
 *Disadvantage* : Not suitable for complex problems

- **NoN - Parametric Models** = Here the model doesnt have any fixed structure and we have to change or retraine the model with more data. . Model can learn the complex patterns 
- *Example*:
- Decision-tree
- K-Nearest Neighbour
- Support Vector Machine

# **Naive Byes**
Naive Byes ek probability - based machine learning algorithm hai jo Byes Theoram pe kaam klarta h . Ye naive(simple) isiliye hota h kyuki ye maan leta h ki saare fetures(inupts) ek dusre se indipendent hota hai (jo ki real life me galta h pr ohir bhi kaam kr jata hai)
**Types**
- **Bernoulili Naive Bayes** : Ye algorithm ham binary(yes or no) problem me use krte h Ex spam yes or no
- **Multinomial naive Byes** : Ye algorithm ham text data ke liye use krte h (ex News Categoriy)
- **Gaussain Naive Byes** : Ye algirthm ham numeric data ke liye use krte h (ex Medical Test)
**Working**
1. Har class ka prior probability calculate kro (ex . 30% emails spam h -> P(spam) = 0.3)
2. Ab kuch likelyhood keywords nikalo (ex FREE word 50% emails me ata h = P(FREE|SPAM) = 0.5)
3. Ab naive assumption lgao(sare features ekdurse se independent h to sabhi me lgao)
   **P(Spam∣"FREE","WIN") ∝ P("FREE"∣Spam) ×P("WIN"∣Spam)× P(Spam)**
4. Jis class ki probability sabse jyada h useme predication kro 

**Pros Cons**
**Pros** : 
Fast hota h or real time me use kiya jata h
 Small data se bhi kaam chala leta h
 **Cons** :
 Independence Assumption(relaistic nahi hai)
Agr koi word training me nahi mila to uski probability 0 ho jati h

**Application** Spam Detection , Sentimental Analysis , Medical Diagnosis













# Unit 5
**Pattern Recognization**
Pattern Recognization ka matlab hai chizo ko phechana - jaise , photo , voice , handrwriting etc
Machino ko train kiya jata hai jisse vo data ke patterns ko smajte h or categories me divide krte hai
example = Spam Email Detection  , Digit Recognization

**Design Principle of Pattern Recognization**
- Invariance = Chote changes pe bhi system data ko phechan le
- Robustness = Thoda noise ya error ho toh bhi sahi output de
- Real Time = Fast kaam kare , time waste na kare 
- Adaptability = Naye data se seeke , or update hojaye
- Simplicity = Design simple easy ho jisse maintain krna easy ho
- Acuracy = Acuurate ho 


**Statistical pattern Recognition**
- Ye ek method he pattern phechanne ka jisme maths or probability ka use hota hai
- System har input ko check karta hai ki vo kis class me jana chahiye 
- Jis class ki probability sabse jyada hoti hai system ko usme daal diya jata hai
- Ye method suoervised learning me use ho ta hai , matlab labeled data hota hai
- Isme system training data se learn karta hai 
- Ex = Spam Detection System, Handwritting Recognization , Face Recognization
- Adv = Acurate 
- Prob = agr data incomeplet ho to wrong prediction 

**LDA** 
Linear Descriminant Analysis 
- LDA ek supervised learning method
- Iska kaam hota hai alag alg classes ko clearly separate krna
- LDA dimension kam kartaa hai but classes ke hisaab se
- Ye data ko ese axis pe project krta hai jha difference jyada ho
- LDA same classes ke points ko paas rakhta hai 
- or Alag classes ke data points ko door rakhta hai
- use := Face Recognization , Text Classification 

**NN(Nearrest Neighbor)**
ye ek supervised learning aglorithm hai jo classification or regression me use hota hia , ye nearest neighbour ko dek ke decision leta hai
**How KNN Work**
- Sabse phele data set me se k nearest neighbour find karo
- unke labels check kro
- Jo labels bar bar ate hai vo new data point ka class hote hai
- ex = k = 3 , and the labels = pass , pass , fail , new data point ke liye label = pass hoga
Advantage = Simple,easy to understand , Work well with smaller data
Disadvantage = Large dataset me slow hota hai , k  value select krna tricky hota hai

**Navie Byes** 
 ek supervised learning algorithm hai jo mainly classification ki problem me use hota hai . Ye algorithm byes theorm pr based hoti hai jiska assumption hota hai feture indipenedent hote hai
 p(class/data) = p(data/class) * p(class) / p(data)
  **Working**
 Trainign data se classprobability and feture problailibty calculate krta hai 
 New data ke liye class probability nikalta hai jiski problaility highest hoti hai use class ko assing krta hai
 EX : Predict student pass or not:
 p(pass/study = Yes , sleep = No)
 Advantage :
 - Simple and fast 
 - large set pe bhi ache se work krta hai
Disadvantage:
- Real world data me fetures aksar depenedenthote hai jisse ye ignore krta hai
- Agr data set me category missing hoti hai to uski probability 0 kr deta hai
applications: 
- Email spam classifer
- News categorization

**SVM**
SVm ek supervised learning agorithm hai jo mainly classification ke liye use hoti hai . 
Iska main goal hota hai ek eisi libne(hyperlink) bana jisse data points ko seprate kiya ja sake
**Working**
- Svm data points ko 2 gorup me divibde krta he
- fir ek best hyper link kheechta hai or data points ko 2 group me devide krta hai  or unke beech me maximum gap banata hai
- Jo data point hyper link ke close hote hai unhe support vectore khete hai
**Types of SVM**
- Linear SVM := jab data points assani se line se alag ho jaye 
- Non Linear SVM := jab data complex hotahai tab svm data ko high dimension me lejakar seperate krta hai
**Advantage**
- SImple or powerfull
- Wok well for high dimension
**Disadvantage**
- Kernal selection , tricky hota hai
- Training time zyada hota hai
- Ex :=> Spam detection , Face detection

**K Means**
K means is a clustering algrothm thatgroups the similar data points together . It does it buy putting the data points together into k different groups based on how close they are from each other


# Unit 4
**SUpervised Learning**
Here the model learn from the labeled data(where both input and output is provided) . It finds the relation between the input and output and make predictions accoridng to it
EX :=> Spam Email Detection
**UNsupervised Learning**
heree te model learns from the unlabeled data(where only input is provided no output is thier) It finds the  hidden clusters and make predictions
EX :=> News categorization


# Decision Tree
Decision tree ek tree jesa structure hota hai jo decision lene ke liye use hota hai , Ye dono regression or classification ki problem ke liye use hota hai . 
**Working**
Root node se start hota ha(y question hota)
har internal node ek condition hota hai
har branch us condition ka result hota hai
orhar leaf node final decision hota hai
**Steps**
**BEst Feture Choose Karna** Sabse phele ham decide krenge ki hamre data ke liye konse feature best h uske liye hum giniIndex ya informatn gain ka use karte hai
**Har Group pr Repeat Kro** Har group ke liye best feature dundna or split karna
**jab tal Leaf Nahi Milta** jab tak final decision nahi mlta process repeat kro
**Advantages**
- Simple and Easy to understand
- Numerica and categorical dono me kaam karta hai
**DIsavantage**
- Overfitting problem
- Small data change se puyra tree change ho jata hai
**Application**
Spam email detection


**Linear Regression** ek supervised learning model hai jo continues output predict karta hai(jese marks , salary , price) 
Ex = House Size -> House Price
     Study Time -> Marks
Formula = > y = mx + c
y = preduicted value , x = input , m = slope , c=  intercept
Types of LInear Regression:
- Simple LR => sirf 1 input variable hota hai
             ex = Marks = f(study time)
- Multiple LR => 2 ya use zyada input variables hote hai
              ex = Marks = f(study time , sleep time , study hourse)
Step of LR :
1. Data collect karo 
2. Line of best fit nikalo using y = mx + c
3. Model train kro
4. Predication karo
5. Accuracy check karo

# Em Algorithm
EM Algo ka matlab h = Expectation Maximization
Purpose : Jab data incomplete ya hidden vairables ke sath hota hai , tab EM algorithm use hoti h parameters estimate karne ke liye
Use cases : Clustering , Missing Data fill karne me , NLP(Natural Language Processing)
*Steps of EM ALgorithm*
- E Step(Expectation Step) = Missing ya hidden data ko guess lagata hai , Probabilites calculate karta hai 
- M Step(Maximization Step) = Guessed values ke basis pe model parameters update karta hain
Iterations: E or M steps baar baar repeat hote hain , Jab tak parameters value stable na ho jaye
Advantage : 
- Incomplete data ke sath kaam karta hai
- Real world applications me use hota hai
Limitation
- Starting values pe depend krta hai
- slow convergence

