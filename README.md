2.2 Ontology design
Beyond the combine ontology, each paper has its own ontology. Below are descriptions of 2 such papers with their visual representation.
(Prefix: ai) Ontology based on the paper ”An Empirical Investigation of Reliance on AI-Assistance in a Noisy-Image Classification Task” by H Tejeda Lemus
et al.
Classes
– AIModel – Represents an AI classifier or system that assists humans (subclass of :ArtificialAgent).
– AIOffCondition / AIOnCondition – Subclasses of experimental conditions indicating whether AI is available to participants.
– Accuracy, AutomationBias, OptimalReliance, ConfidenceRating –
Subclasses of PerformanceMetric, capturing accuracy, bias, reliance gap,
and confidence levels in AI-human interaction.
– ClassifierAboveBaseline, ClassifierBelowBaseline, ClassifierOnBaseline – AI model categories indicating their performance relative to a human
baseline.
– ExperimentalCondition – Describes experimental conditions that can be
assigned to tasks (e.g., AI on/off).
– NoisyImageClassificationTask – A subclass of :InteractionTask, representing decision-making tasks under uncertainty.
– Participant – Human subjects involved in AI-assisted tasks.
– PerformanceMetric – Captures metrics for evaluating performance of AI
models or human participants.
4 Tomasz Kubrak and Rafa l Kukie lka
Fig. 1. Ontology from noisy image classification paper by H. Tejeda Lemus et al.
Object Properties
– achievedMetric – Links a NoisyImageClassificationTask to a PerformanceMetric
describing task performance.
– hasCondition – Associates a task with its experimental condition (AIOffCondition
or AIOnCondition).
– involvesParticipant – Links tasks to the Participant involved.
– usesAIModel – Specifies which AIModel is used during a given task.
Data Properties
– hasAccuracyValue – Numeric accuracy of a model or task outcome (range:
xsd:decimal).
– hasAutomationBiasScore – A float score indicating participant’s susceptibility to automation bias.
– hasConfidenceValue – Decimal or float expressing AI’s or human’s confidence level in decisions.
Multi-Domain Ontology for HI 5
– hasOptimalRelianceGap – A float measure of deviation between actual
and optimal decision-making performance.
Named Individuals
– aiAssistancePaper – A :Paper entity describing the empirical study on
AI reliance in noisy image classification.
– classifier above baseline, classifier on baseline, classifier below baseline
– Concrete AI classifiers representing different relative performance levels.
– condition ai off, condition ai on – Specific conditions denoting availability of AI support.
– participant 001, participant 002 – Sample participants annotated with
hasAutomationBiasScore and hasOptimalRelianceGap.
– task p1 t1, task p2 t1 – Instances of NoisyImageClassificationTask,
each linked to specific conditions and performance metrics.
Generative VR (:gv) Ontology based on the paper ”“Computer, Generate!”
– Investigating User-Controlled Generation of Immersive Virtual Environments”
by C. Liebers et al.
Classes
AllAtOnceFlow A subclass of ControlFlow, describing a flow where the entire
environment is generated at once.
ColoringStep A subclass of GenerationStep, representing a stage where an
object’s color or appearance is applied or changed.
ControlFlow The base class for specifying how generation steps are orchestrated
or executed in a scenario.
ControllerInput A subclass of InteractionModality, indicating VR controllerbased interaction.
CreationBeforeManipulationFlow A subclass of ControlFlow, describing a
flow where creation of objects occurs before adjustments or manipulations.
CreationStep A subclass of GenerationStep, representing the step of object
creation or spawning in VR.
DeletionStep A subclass of GenerationStep, representing the step of deleting
or removing an object.
EnvironmentGeneration A subclass of :Scenario, modeling an overall environmentgeneration process or task.
EvaluationMetric A general class for evaluation or performance metrics in
generative VR contexts.
GenerationStep The base class for individual steps in the generation of VR
objects.
HandInput A subclass of InteractionModality, representing hand-tracking or
gesture-based interaction in VR.
InteractionModality A subclass of :InteractionMethod, indicating a particular modality for user interaction.
6 Tomasz Kubrak and Rafa l Kukie lka
Fig. 2. Ontology from Virtual Environments paper by C. Liebers et al.
MovementStep A subclass of GenerationStep, representing translation or movement of objects in VR.
Participant A subclass of :Human, describing a human user or study participant in a VR environment.
ScalingStep A subclass of GenerationStep, indicating a step in which an object’s size is changed.
SpatialAccuracy A subclass of EvaluationMetric, representing accuracy metrics for positional or rotational user actions.
StepByStepFlow A subclass of ControlFlow, describing a control flow where
objects are created and manipulated one by one.
TaskCompletionTime A subclass of EvaluationMetric, indicating the amount
of time required for a specific generation task.
UsabilityScore A subclass of EvaluationMetric, representing usability-related
metrics in generative VR.
UserExperienceScore A subclass of EvaluationMetric, representing user experience metrics in generative VR.
VoiceInput A subclass of InteractionModality, describing voice-based commands for VR generation.
Object Properties
Multi-Domain Ontology for HI 7
achievedResult An object property linking a generation process or environment to an EvaluationMetric.
employsGenerationStep Object property from EnvironmentGeneration to Generation
Step, indicating which generation steps the environment uses.
hasControlFlow An object property defining which ControlFlow is used in a
generation scenario.
hasModality An object property denoting the InteractionModality (e.g., controller, hand, or voice).
involvesParticipant Links an environment or generation scenario to the Participant
involved.
Data Properties
hasRotationError A xsd:float data property within SpatialAccuracy, indicating rotational mismatch.
hasSUSScore A xsd:float data property within UsabilityScore, capturing a
system usability scale value.
hasTimeInSeconds A xsd:float data property within TaskCompletionTime,
capturing total time in seconds.
hasTranslationError A xsd:float data property within SpatialAccuracy,
indicating positional offset.
hasUEQScore A xsd:float data property within UserExperienceScore, capturing a user experience questionnaire result.
Instances
VR GardenStudy An individual of EnvironmentGeneration, describing a usercontrolled environment generation study (the “garden” scenario). Uses employs
GenerationStep for the five steps (creation, movement, etc.), hasControlFlow
for three flows (all-at-once, creation-before-manipulation, step-by-step), has
Modality for controller, hand, voice, and involvesParticipant for study
participants.
all at once flow A AllAtOnceFlow object. The environment is generated in
one request.
coloring step A ColoringStep object. Step where user applies or changes
object colors.
controller input modality A ControllerInput object. Indicates VR controller usage for environment generation tasks.
creation before manipulation flow A CreationBeforeManipulationFlow object. Allows generating multiple objects first, then adjusting them.
creation step A CreationStep object. Step for creating new virtual objects.
deletion step A DeletionStep object. Step for removing objects from the
environment.
hand input modality A HandInput object. Hand tracking or pinch gestures for
environment tasks.
movement step A MovementStep object. Step for repositioning objects.
scaling step A ScalingStep object. Step for resizing objects.
8 Tomasz Kubrak and Rafa l Kukie lka
step by step flow A StepByStepFlow object. Process of generating and editing each object one at a time.
study participant 001 A Participant object. Illustrative participant in the
VR environment generation study.
voice input modality A VoiceInput object. Uses voice commands, especially
for object creation.
