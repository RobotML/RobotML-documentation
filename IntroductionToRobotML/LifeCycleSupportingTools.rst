Supporting Life cycle through associated tools
----------------------------------------------

Presentation
^^^^^^^^^^^^

As it is presented in the previous page there is a need to implement the life cycle 
in the actual existing tools provided to the different types of users. The following picture details them.


.. figure:: ./LifeCycleSupportingTools_images/D0.11-P0.8-P12.7-Dissemination-4.png
   :align: center
   :width: 500
   :alt: Life Cycle and supporting tools

   *How life cycle is implemented*

short stories
^^^^^^^^^^^^^

Before entering in the niceties of the tools and life cycle, here follows two short stories to illustrate what is the meaning between all these beautiful words and wishes.

Betty and the navaid
____________________

We are introducing her Betty. She is working for a car company willing to provide to the market a new navigation aid based
upon the interaction between the driver and a talking counterpart in the car. She discussed with the marketing department 
that explains why it would like to see such an aid and what would be the functionalities. She then discuss with the technical
team that delivers constraints onto the system and the targeted system.
Knowing the Robotic portal, she already has an account allowing her to ask for a new space in it where she will be able to 
create a problem. She characterises its access properties stating it is public for what concerns scenario and problem presentation.
Those in charge of the portal, considering the information delivered agree on the creation of this space and then Betty is able
to begin her job.

She then upload to the portal through the defined channel and a space she wanted to be public a document describing what she 
needs the system to do and a video to illustrate it. She opens now the :term:`RobotML` platform in order to model the scenario, specifying
her robot car, its associated system and the urban environment in which the scenario will take place. She precises in the model what
should be measured through probes providing also a description of the criteria that will be derived of these metrics. Then, working
with her IT department, she devised the generator and the environment models (libraries implementing walkers dynamic, car cinematic,
lights, sensors physics, ...) allowing her to create a simulator in which the scenario can be shown. She verifies that she will be able
generate directly from the simulator to her actual car robot system and uploads in a less public space this simulator and advertises
video of it, presentation of the RobotML models and refined textual description of the metrics and criteuria used.

She waits for some time now seeing nonetheless that many people downloaded the scenario and videos. Some weeks later, she receives
two requests from two academics and one SME willing to use the simulator to try some solutions on her problem. She discards one of
the academic because the technology they are promoting is not inline with the main trend in her IT team and provides to the two
other ones access to the simulator. Being able to issue such requests means implicitely that those Roboticians already have an account
on the portal and thus request being accepted means for them to dispose of a specific webspace on the portal where they will be able
to provide their solutions.

At this point many exchanges exist between Betty and these teams trying to understand what was the problem. As one of the solution
needs an adaptation of the interfaces, Betty reissues an updated version of the simulator updating the model at the same time.

Some months later, the teams provides their solutions showing their results on the simulator using the criteria. Betty finds that the
academic is better but nevertheless proposes to the two of them to show their solution on the actual robot. Meetings are held and
test period is defined. Thanks to the possibility to generate directly to the Car navaid system, time to implement solutions is small
enough.

One month later Betty can choose the academic solution and begins private discussions outside the portal scope in order to define IP
and royalties with the final academic. This one not willing to work directly with a big company first transfer the knowledge to the SME
that was competing with it.

And thus in a period of one year, Betty is able to tell her company that the new navaid system is ready to come out to the public as a
release of the car navaid system.


Richard and his PhD
___________________

Richard is now in his second year of his PhD thesis which subject is an advanced servoing algorithm merging Radar and visual data
to offer a proved and reliable localisation system in a urban environment. Unhappily, in his own testing environment he is unable
to show flexibility of his methodology and associated implementation (urban car in some not very dense area). He goes to portal and
shuffles through the proposed problems. Three are attracting his attention:

-	A car manufacturer is proposing a problem in which the represented environment and associated sensors are very close to those he is using but more realistic;
-	An aircraft manufacturer is having problems for its aircraft to manoeuvre on not well known airports;
-	There are some new EM sensors that could be used onto humanoïd robots and perhaps their precision could be enough to allow the algorithm to wor. This problem is offered by a well known French Laboratory.

Richard won't be able to address each problem in his PhD time frame thus he needs more information than those proposed in the public part of these problems.
Thus, as he already had an account on the portal, he send the needed forms as provided by the three problem's providers in order to access them completely.
He is now able to download a complete description and most importantly, their models.
Shuffling through the three of them, he identified very soon that unhappily it would be very difficult to adapt the aircraft system model to integrate his algorithm proposal.
On the contrary, Work onto the car system seems really easy and with work, adaptation to humanoïd is possible.

Considering the first case, Richard now download the latest version of the :term:`RobotML` platform and opens the car :term:`problem`\ .
He can directly identify the component that would host his algorithm. Interface is almost the same but not exactly.
Deciding not to optimise code, he introduces in the model a type translation component that adapts inputs to his algorithm needs.
Then as there is no need on the output, he generates thanks to the platform using generator provided by the car :term:`problem` :term:`provider` a new simulator that includes his algorithm.
As it is he is now able to run tests and stores the data using the already defined probes and creating the metrics as defined in the problem description.
Now using the criteria, he sees that he improves not so marginally localisation accuracy allowing the car to use less large roads.
At this step he requests the :term:`portal` responsible permission to open a :term:`solution` page for him to record his results and do it.
He publishes his achievements in th eproper review and goes on developing the theory associated with the algorithm using the insights gained thanks to the experimentation.

Considering the second case, due to his Thesis work, Richard postpones the integration to future times.
Three months before delivering his text to reviewers and willing to ease his mind he goes back to his idea to test the algorithm onto humanoïd.
He again asks for permission to use the problem as his lease was time suspended.
Again he obtained this permission from the :term:`problem` :term:`provider` and using his existing version of the platform opens the model in order to better understand the :term:`robot` system.
It really has to be adapted to accept his algorithm as the EM :term:`sensors <sensor>` are not providing the same type of information as those he waited for;
Moreover, synchronisation needed between the two types of sensors is not at all the same.
Richard adapts the model many times discussing with the :term:`problem` :term:`provider` in order to understand what some parts of the architecture are meaning.
After some efforts and adaptations at the limit of the system capability he is able to generate the complete robot application.
Doing the same job as previously he is able to issue results to oppose to the criteria defined and there he sees the limits of the algorithm tested.
Discussing with the :term:`provider` he sees a complete new way to understand the theory leading to a major update of the software.
There again Richard opens a :term:`solution`space and uploads his solution.

At this step, he considers that it could be a good idea to provide this code to the community and asks for opening a :term:`module` :term:`provider` space.
When opened, he related this module to the two solutions developed and provide the model of the interface to be used inside the platform to be able to insert the algorithm in any other :term:`problem`.
Eventually he also provieds the source code through a packaged file and a C library on x86 architecture.

It's time now to present his final results in front of his PhD Jury.
All goes smoothly but during the questions time, in the audience, someone requests some specific explanations onto the determinism of the solution and if it could be embedded in some limited memory architecture.
Answering positively, Richard is surprised after the Jury felicited him to be proposed a job from the questioner in order to come in the car company that provided the :term:`problem`\ .

Presentation of each step and suppporting tooling
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

These two stories are happy ones for sure and shows the type of impact that can be achieved if Robotic community agrees to use such a portal and its associated tools.

Formal Robotician Portal
________________________

This portal is the first supporting tool and a very important one. In fact it is the place where everything can be exchanged, worked between :term:`providers <provider>` and :term:`users <user>`\ .
It manages the access, provides the  different needed spaces, :term:`SVN` services, implements the life cycle.

:term:`RobotML`
_______________

This tool is not usable in itself as it is the definition of the language that is implemented in the tool to come. 
Nevertheless, the definition of this language is not to be confused with its implementation through any tool.
Anybody able to answer this definition can provide model (either :term:`problem` or :term:`solution`).

:term: