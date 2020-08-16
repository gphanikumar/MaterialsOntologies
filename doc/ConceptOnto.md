# ConceptOnto

Here we document the ontology ConceptOnto. This ontology will represent the following aspects of Materials Domain: Concepts, Behavior, Parameters, Tools, Techniques, Processes and Defects. The different classes defined in this ontology and the relationships will be detailed here. 

Following prefix is used for individuals in this page.
    PREFIX mc: <http://semantic.iitm.ac.in/ConceptOnto/MaterialsConcepts#>

## Classes
All instances in the ontology ConceptOnto will fall into the following classes.
Equivalent class definitions are defined based on certain relationships as described below.

### Behavior
The class mc:Behavior has instances that indicate behavior of materials such as physical phenomena. For example:
    mc:AlloySolidification is an instance under the class mc:Behavior
As of now, instances are defined under SubClasses such as Cracking, Deformation, Diffraction, Diffusion, Fluid Flow, Heat Transfer, Mass Transfer, Phase Change, Reaction, Thermodynamic Equilibrium and Transport Phenomena.

Transport Phenomena is a SubClass which is a union of Diffusion, Fluid Flow, Heat Transfer, Mass Transfer and Reaction.

### Concept
The class mc:Concept has instances that indicate a physical understanding or representation of a behavior. SubClasses defined are Criterion, Dimensionless Number, Effects, Equation, Instability, Laws, Mechanism, Model, Paradox, Principles, Relation, Rules, Theorem and Theory. For example:
    mc:AbsoluteStabilityCriterion is an instance under the class mc:Concept

### Defect
The class mc:Defect has instances that indicate a defect that arises typically due to processing. For example:
    mc:ChevronCracking is an instance under the class mc:Defect

### Parameters
The class mc:Parameters has instances that indicate parameters, variables, constants and process conditions that are useful in describing a process or in defining concept or an equation. For example:
    mc:MassDensity is an instance under the class mc:Parameters
As for now, parametesr are organized in Subclasses such as Empirical, Measured Quantity, Model Parameter, Physical Property, Process Condition, Thermodynamic Property and Universal Constants.

### Process
The class mc:Process has instances that indicate different processing techniques used in the materials domain. For example:
    mc:InvestmentCasting is an instance under the class mc:Process
As of now, processes are organized in SubClasses such as Bulk Deformation Processes, Casting Processes, Grinding Processes, High Energy Rate Forming, Machining, Sheet Metal Working and Welding.

### Technique
The class mc:Technique has instances that indicate a way to use a tool to calculate or experimentally measure a parameter. For example:
    mc:CALPHAD is an instance under the class mc:Technique

### Tool
The class mc:Tool has instances that can be either Computational or Experimental in nature. The instances are organized under these two SubClasses for convenience. For example:
    mc:ThermoCalc is an instance under the classes mc:Tool and mc:ComputationalThermodynamics
    mc:OpticalMicroscope is an instance under the classes mc:Tool and mc:Experimental

## Object properties

 * Concepts have equations involving parameters. Conversely, a parameter is involved in the equation for a concept.
      mc:hasEquationInvolving has mc:Concept as Domain and mc:Parameters as Range
      mc:isInvolvedInEquationFor is an inverse of this property.
 * Concepts could involve certain behavior of materials. Conversely, a behavior could invole a certain concept as per our understanding.
      mc:isApplicableDuring has mc:Concept as Domain and mc:Behavior as Range
      mc:couldInvove is an inverse of this property.



