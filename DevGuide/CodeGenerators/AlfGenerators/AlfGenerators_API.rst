.. _Alf_Gen_API

=====================
The Alf Generator API
=====================

In RobotML, the :term:`Alf<alf>` language is used to describe the operation contents (only OpaqueBehavior). This language permit to have a generic modeling and generate it easily in more other langauge.  

For your needs, you can create a specific :term:`Alf<alf>` generator language on using this :ref:`Alf Generator API<_Alf_Gen_API>`.

::warning:: The :term:`Alf<alf>` knowkedge is clearly recommended. Go to see the Alf language site before start your work!

Overview
########

.. image:: ../ATK_Scenario_images/Alf_overview.png
   :align: center
   :alt: Alf API overview.
   
.. AlfServcies::

AlfServices
***********

The module **AlfServices** contains all the methods to translate RobotML element to functional code.

*public*

**public static org.eclipse.papyrus.uml.alf.alf.Block createAlfBloc(org.eclipse.papyrus.uml2.NamedElement element)**

   +---------+----------------------------------------------------------------+
   | element | UML element model.                                             |
   +---------+----------------------------------------------------------------+
   | return  | Return an Alf Bloc corresponding to the UML element parameter. |
   +---------+----------------------------------------------------------------+

Create an Alf bloc code from an Opaque behavior UML element.

**public static String translateAlfBlocTo_Athena(org.eclipse.papyrus.uml.alf.alf.Block bloc)**

   +---------+-----------------------------------------------------+
   | bloc    | Alf bloc to translate.                              |
   +---------+-----------------------------------------------------+
   | return  | Return the alf bloc translation on Athena language. |
   +---------+-----------------------------------------------------+

Translate an Alf bloc to Athena code.

**public static String translateAlfBlocTo_CPP(org.eclipse.papyrus.uml.alf.alf.Block bloc)**

   +---------+--------------------------------------------------+
   | bloc    | Alf bloc to translate.                           |
   +---------+--------------------------------------------------+
   | return  | Return the alf bloc translation on C++ language. |
   +---------+--------------------------------------------------+

Translate an Alf bloc to C++ code.

.. AlfBlock::

AlfBlock
********

.. TODO:: Definition

*public*

**AlfBlock(org.eclipse.papyrus.uml.alf.alf.Block bloc)**

   +---------+--------------------+
   | bloc    | Original Alf bloc. |
   +---------+--------------------+
   
Constructor, the alf bloc is mandatory, it will be transmited to the genrators.

**void generateTo(IAlfGenerator generator)**

   +-----------+---------------------+
   | generator | Translate generator |
   +-----------+---------------------+

Call the Alf translation on using the generator parameter to work.

**org.eclipse.papyrus.uml.alf.alf.Block getBlock()**
  
  +-----------+------------------------------+
  | return    | Return the original Alf bloc |
  +-----------+------------------------------+
  
Return the Alf bloc to get the original information.

**void setCodeTranslation(String code)**

   +-----------+--------------------------------------+
   | code      | Code string to append on the result. |
   +-----------+--------------------------------------+
   
Append the code string parameter on the code string result. 

**String getCodeTranslation()**

   +-----------+--------------------------------+
   | return    | Return the code string result. |
   +-----------+--------------------------------+
   
Return the code string translation result. 

.. IAlfGenerator::

IAlfGenerator
*************

Alf generator interface, contains the mandatory method to implement for the Alf generator.

*public*

**abstract void generate(AlfBlock bloc)**

   +-----------+------------------------+
   | bloc      | Alf bloc to translate. |
   +-----------+------------------------+
   
Abstract method to redefine in implementation. Translate the Alf bloc.

.. AlfGenerator::

AlfGenerator
************

Abstract Alf base generator. Contains the common method for all Alf generators. It implement the :ref:`IAlfGenerator <IAlfGenerator>` interface.

*public*

**abstract void generate(AlfBlock bloc)**

   +-----------+------------------------+
   | bloc      | Alf bloc to translate. |
   +-----------+------------------------+
   
Translate the Alf bloc.

*protected*

**String generateAlfBlock(Block bloc)**

   +-----------+------------------------+
   | bloc      | Alf bloc to translate. |
   +-----------+------------------------+
   | return    | Alf bloc translation.  |
   +-----------+------------------------+

Return the Alf bloc translation.   

**String generateStatementSequence(StatementSequence aStatementSequence)**

   +--------------------+--------------------------------------+
   | aStatementSequence | Alf statement sequence to translate. |
   +--------------------+--------------------------------------+
   | return             | Alf statement sequance translation.  |
   +--------------------+--------------------------------------+

Return the Alf statement sequence translation.

**String generateDocumentedStatement(DocumentedStatement aDocumentedStatement)**

   +----------------------+---------------------------------------+
   | aDocumentedStatement | Alf documented statment to translate. |
   +----------------------+---------------------------------------+
   | return               | Alf documented statment translation.  |
   +----------------------+---------------------------------------+

Return the Alf documeneted statment translation.

**String generateSequenceStatement(Statement aStatement)**

   +----------------------+----------------------------+
   | aStatement           | Alf statment to translate. |
   +----------------------+----------------------------+
   | return               | Alf statment translation.  |
   +----------------------+----------------------------+

Return the Alf documeneted statment translation.

**String generateStatement(Statement aStatement)**

   +----------------------+----------------------------+
   | aStatement           | Alf statment to translate. |
   +----------------------+----------------------------+
   | return               | Alf statment translation.  |
   +----------------------+----------------------------+

Return the Alf documeneted statment translation.

**String generateInlineStatement(InlineStatement aInlineStatement)**

   +----------------------+-----------------------------------+
   | aInLineStatement     | Alf inline statment to translate. |
   +----------------------+-----------------------------------+
   | return               | Alf inline statment translation.  |
   +----------------------+-----------------------------------+

Return the Alf inline statment translation.
   
**String generateAnnotatedStatement(AnnotatedStatement aAnnotatedStatement)***

   +----------------------+--------------------------------------+
   | aAnnotatedStatement  | Alf annotated statment to translate. |
   +----------------------+--------------------------------------+
   | return               | Alf annotated statment translation.  |
   +----------------------+--------------------------------------+

Return the Alf annotated statment translation.

**String generateBlockStatement(BlockStatement aBlockStatement)**

   +----------------------+----------------------------------+
   | aBlockStatement      | Alf block statment to translate. |
   +----------------------+----------------------------------+
   | return               | Alf block statment translation.  |
   +----------------------+----------------------------------+

Return the Alf block statment translation.

**String generateEmptyStatement(EmptyStatement aEmptyStatement)**
   
   +----------------------+----------------------------------+
   | aEmptyStatement      | Alf empty statment to translate. |
   +----------------------+----------------------------------+
   | return               | Alf empty statment translation.  |
   +----------------------+----------------------------------+

Return the Alf empty statment translation.

**String generateIfStatement(IfStatement aIfStatement)**

   +----------------------+-------------------------------+
   | aIfStatement         | Alf if statment to translate. |
   +----------------------+-------------------------------+
   | return               | Alf if statment translation.  |
   +----------------------+-------------------------------+

Return the Alf if statment translation.

**String generateSequentialClausesTemplate(SequentialClauses aSequentialClauses)**
   
   +----------------------+--------------------------------------+
   | aSequentialClauses   | Alf sequential clauses to translate. |
   +----------------------+--------------------------------------+
   | return               | Alf sequential clauses translation.  |
   +----------------------+--------------------------------------+

Return the Alf sequential clauses translation.

**String generateConcurrentClausesTemplate(ConcurrentClauses aConcurrentClauses)**

   +----------------------+--------------------------------------+
   | aConcurrentClauses   | Alf concurrent clauses to translate. |
   +----------------------+--------------------------------------+
   | return               | Alf concurrent clauses translation.  |
   +----------------------+--------------------------------------+

Return the Alf concurrent clauses translation.

**String generateNonFinalClauseTemplate(NonFinalClause aNonFinalClause)**

   +----------------------+------------------------------------+
   | aNonFinalClause      | Alf non final clause to translate. |
   +----------------------+------------------------------------+
   | return               | Alf non final clause translation.  |
   +----------------------+------------------------------------+

Return the Alf non final clause translation.

**String generateFinalClauseTemplate(FinalClause aFinalClause)**

   +----------------------+--------------------------------+
   | aFianalClause        | Alf final clause to translate. |
   +----------------------+--------------------------------+
   | return               | Alf final clause translation.  |
   +----------------------+--------------------------------+

Return the Alf fianl clause translation.

**String generateSwitchStatement(SwitchStatement aSwitchStatement)**

   +----------------------+------------------------------------+
   | aSwitchStatement     | Alf switch statement to translate. |
   +----------------------+------------------------------------+
   | return               | Alf switch statement translation.  |
   +----------------------+------------------------------------+

Return the Alf switch statement translation.

**String generateSwitchDefaultclause(SwitchDefaultClause aSwitchDefaultClause)**

   +----------------------+-----------------------------------------+
   | aSwitchDefaultClause | Alf switch default clause to translate. |
   +----------------------+-----------------------------------------+
   | return               | Alf switch default clause translation.  |
   +----------------------+-----------------------------------------+

Return the Alf switch default clause translation.

**String generateSwitchClause(SwitchClause aSwitchClause)**

   +----------------------+---------------------------------+
   | aSwitchClause        | Alf switch clause to translate. |
   +----------------------+---------------------------------+
   | return               | Alf switch clause translation.  |
   +----------------------+---------------------------------+

Return the Alf switch clause translation.

**String generateSwitchCase(SwitchCase aSwitchCase)**

   +----------------------+-------------------------------+
   | aSwitchCase          | Alf switch case to translate. |
   +----------------------+-------------------------------+
   | return               | Alf switch case translation.  |
   +----------------------+-------------------------------+

Return the Alf switch case translation.

**String generateNonEmptyStatementSequence(NonEmptyStatementSequence aNonEmptyStatementSequence)**

   +----------------------------+------------------------------------------------+
   | anonEmptyStatementSequence | Alf non empty statement sequence to translate. |
   +----------------------------+------------------------------------------------+
   | return                     | Alf non empty statement sequence translation.  |
   +----------------------------+------------------------------------------------+

Return the Alf non empty statement sequence translation.

**String generateWhileStatement(WhileStatement aWhileStatement)**

   +----------------------+-----------------------------------+
   | aWhileStatement      | Alf while statement to translate. |
   +----------------------+-----------------------------------+
   | return               | Alf while statement translation.  |
   +----------------------+-----------------------------------+

Return the Alf while statement translation.

**String generateDoStatement(DoStatement aDoStatement)**

   +----------------------+--------------------------------+
   | aDoStatement         | Alf do statement to translate. |
   +----------------------+--------------------------------+
   | return               | Alf do statement translation.  |
   +----------------------+--------------------------------+

Return the Alf do statement translation.

**String generateForStatement(ForStatement aForStatement)**

   +----------------------+---------------------------------+
   | aForStatement        | Alf for statement to translate. |
   +----------------------+---------------------------------+
   | return               | Alf for statement translation.  |
   +----------------------+---------------------------------+

Return the Alf for statement translation.

**String generateBreakStatement(BreakStatement aBreakStatement)**

   +----------------------+-----------------------------------+
   | aBreakStatement      | Alf break statement to translate. |
   +----------------------+-----------------------------------+
   | return               | Alf break statement translation.  |
   +----------------------+-----------------------------------+

Return the Alf break statement translation.

**String generateReturnStatement(ReturnStatement aReturnStatement)**

   +----------------------+------------------------------------+
   | aReturnStatement     | Alf return statement to translate. |
   +----------------------+------------------------------------+
   | return               | Alf return statement translation.  |
   +----------------------+------------------------------------+

Return the Alf return statement translation.

**String generateAcceptStatement(AcceptStatement aAcceptStatement)**

   +----------------------+------------------------------------+
   | aAcceptStatement     | Alf accept statement to translate. |
   +----------------------+------------------------------------+
   | return               | Alf accepet statement translation. |
   +----------------------+------------------------------------+

Return the Alf accept statement translation.

**String generateClassifyStatement(ClassifyStatement aClassifyStatement)**

   +----------------------+--------------------------------------+
   | aClassifyStatement   | Alf classify statement to translate. |
   +----------------------+--------------------------------------+
   | return               | Alf classify statement translation.  |
   +----------------------+--------------------------------------+

Return the Alf classify statement translation.

**String generateInvocationOrAssignementOrDeclarationStatement(InvocationOrAssignementOrDeclarationStatement aInvocationOrAssignementOrDeclarationStatement)**

   +------------------------------------------------+----------------------------------------------------------------------+
   | aInvocationorAssignementOrDeclarationStatement | Alf invocation or assignement or declaration statement to translate. |
   +------------------------------------------------+----------------------------------------------------------------------+
   | return                                         | Alf invocation or assignement or declaration statement translation.  |
   +------------------------------------------------+----------------------------------------------------------------------+

Return the Alf  invocation, or assignement, or declaration, statement translation.

**String generateVariableDeclarationCompletion(VariableDeclarationCompletion aVariableDeclarationCompletion)**

   +--------------------------------+---------------------------------------------------+
   | aVaraibleDeclarationCompletion | Alf variable declaration completion to translate. |
   +--------------------------------+---------------------------------------------------+
   | return                         | Alf variable declaration completion translation.  |
   +--------------------------------+---------------------------------------------------+

Return the Alf variable declaration completion  translation.

**String generateAssignmentCompletion(AssignmentCompletion aAssignmentCompletion)**

   +------------------------+------------------------------------------+
   | aAssignementCompletion | Alf assignement completion to translate. |
   +------------------------+------------------------------------------+
   | return                 | Alf assignement completion translation.  |
   +------------------------+------------------------------------------+

Return the Alf assignement completion translation.

**String generateAssignmentOperator(AssignmentOperator aAssignmentOperator)**

   +----------------------+----------------------------------------+
   | aAssignementOperator | Alf assignement operator to translate. |
   +----------------------+----------------------------------------+
   | return               | Alf assignement operator translation.  |
   +----------------------+----------------------------------------+

Return the Alf assignement operator translation.

**String generateSuperInvocationStatement(SuperInvocationStatement aSuperInvocationStatement)**

   +---------------------------+----------------------------------------------+
   | aSuperInvocationStatement | Alf super invocation statement to translate. |
   +---------------------------+----------------------------------------------+
   | return                    | Alf super invocation translation.            |
   +---------------------------+----------------------------------------------+

Return the Alf super invocation statement translation.

**String generateSuperInvocationExpression(SuperInvocationExpression aSuperInvocationExpression)**

   +----------------------------+-----------------------------------------------+
   | aSuperInvocationExpression | Alf super invocation expression to translate. |
   +----------------------------+-----------------------------------------------+
   | return                     | Alf super invocation expression translation.  |
   +----------------------------+-----------------------------------------------+

Return the Alf super invocation expression translation.

**String generateOperationCallExpression(OperationCallExpression aOperationCallExpression)**

   +--------------------------+---------------------------------------------+
   | aOperationCallExpression | Alf operation call expression to translate. |
   +--------------------------+---------------------------------------------+
   | return                   | Alf operation call expression translation.  |
   +--------------------------+---------------------------------------------+

Return the Alf operation call expression translation.

**String generateTupleTemplate(Tuple aTuple)**

   +----------+-------------------------+
   | aTuple   | Alf tuple to translate. |
   +----------+-------------------------+
   | return   | Alf tuple translation.  |
   +----------+-------------------------+

Return the Alf tuple translation.
   
**String generateTupleElement(TupleElement aTupleElement)**

   +---------------+---------------------------------+
   | aTupleElement | Alf tuple element to translate. |
   +---------------+---------------------------------+
   | return        | Alf tuple element translation.  |
   +---------------+---------------------------------+

Return the Alf tuple element translation.

**String generateOperationCallExpressionWithoutDot(OperationCallExpressionWithoutDot aOperationCallExpressionWithoutDot)**

   +------------------------------------+---------------------------------------------------------+
   | aOperationCallExpressionWithoutDot | Alf operation call expression without dot to translate. |
   +------------------------------------+---------------------------------------------------------+
   | return                             | Alf operation call expression without dot translation.  |
   +------------------------------------+---------------------------------------------------------+

Return the Alf operation call expression without dot translation.

**String generateThisInvocationStatement(ThisInvocationStatement aThisInvocationStatement)**

   +--------------------------+---------------------------------------------+
   | aThisInvocationstatement | Alf this invocation statement to translate. |
   +--------------------------+---------------------------------------------+
   | return                   | Alf this invocation statement translation.  |
   +--------------------------+---------------------------------------------+

Return the Alf this invocation statement translation.

**String generateInstanceCreationInvocationStatement(InstanceCreationInvocationStatement aInstanceCreationInvocationStatement)**

   +--------------------------------------+----------------------------------------------------------+
   | aInstanceCreationinvocationStatement | Alf instance creation invocation statement to translate. |
   +--------------------------------------+----------------------------------------------------------+
   | return                               | Alf instance creation invocation statement translation.  |
   +--------------------------------------+----------------------------------------------------------+

Return the Alf instance creation invocation statement translation.

**String generateAnnotation(Annotation aAnnotation)**

   +-------------+------------------------------+
   | aAnnotation | Alf annotation to translate. |
   +-------------+------------------------------+
   | return      | Alf annotation translation.  |
   +-------------+------------------------------+

Return the Alf annotation translation.

**String generateExpressionForm(Expression aExpression)**

   +-------------+------------------------------+
   | aExpression | Alf expression to translate. |
   +-------------+------------------------------+
   | return      | Alf expression translation.  |
   +-------------+------------------------------+

Return the Alf expression translation.

**String generateSequenceExpressionForm(EList<Expression> list)**

**String generateConditionalTestExpression(ConditionalTestExpression aConditionalTestExpression)**

**String generateConditionalOrExpression(ConditionalOrExpression aConditionalOrExpression)**
   
**String generateConditionalAndExpression(ConditionalAndExpression aConditionalAndExpression)**

**String generateInclusiveOrExpression(InclusiveOrExpression aInclusiveOrExpression)**

**String generateExclusiveOrExpression(ExclusiveOrExpression aExclusiveOrExpression)**

**String generateAndExpression(AndExpression aAndExpression)**

**String generateEqualityExpression(EqualityExpression aEqualityExpression)**

**String generateClassificationExpression(ClassificationExpression aClassificationExpression)**

**String generateSequenceConstructionOrAccessCompletion(SequenceConstructionOrAccessCompletion aSequenceConstructionOrAccessCompletion)**

**String generateQualifiedNamePath(QualifiedNamePath aQualifiedNamePath)**

**String generateUnqualifiedName(UnqualifiedName aUnqualifiedName)**

**String generateTemplateBinding(TemplateBinding aTemplateBinding)**

**String generateRelationalExpression(RelationalExpression aRelationalExpression)**

**String generateShiftExpression(ShiftExpression aShiftExpression)**

**String generateAdditiveExpression(AdditiveExpression aAdditiveExpression)**
   
**String generateMultiplicativeExpression(MultiplicativeExpression aMultiplicativeExpression)**

**String generateUnaryExpression(UnaryExpression aUnaryExpression)**

**String generatePrimaryExpression(PrimaryExpression aPrimaryExpression)**

**String generateValueSpecification(ValueSpecification aValueSpecification)**

**String generateThisExpression(ThisExpression aThisExpression)**

**String generateNullExpression(NullExpression aNullExpression)**

**String generateParenthesizedExpression(ParenthesizedExpression aParenthesizedExpression)**

**String generateNonLiteralValueSpecification(NonLiteralValueSpecification aNonLiteralValueSpecification)**

**String generateInstanceCreationExpression(InstanceCreationExpression aInstanceCreationExpression)**

**String generateQualifiedNameWithBinding(QualifiedNameWithBinding aQualifiedNameWithBinding)**
   
**String generateSequenceConstructionCompletion(SequenceConstructionCompletion aSequenceConstructionCompletion)**

**String generateLiteral(LITERAL aLITERAL)**

**String generateIntegerLiteral(INTEGER_LITERAL aINTEGER_LITERAL)**

**String generateStringLiteral(STRING_LITERAL aSTRING_LITERAL)**

**String generateBooleanLiteral(BOOLEAN_LITERAL aBOOLEAN_LITERAL)**

**String generateNumberLiteral(NUMBER_LITERAL aNUMBER_LITERAL)**

**String generateUnlimitedLiteral(UNLIMITED_LITERAL aUNLIMITED_LITERAL)**

**String generateSuffixExpression(SuffixExpression aSuffixExpression, String dot_or_arrow)**

**String generatePropertyCallExpression(PropertyCallExpression aPropertyCallExpression)**

**String generateLinkOperationExpression(LinkOperationExpression aLinkOperationExpression)**

**String generateLinkOperationTuple(LinkOperationTuple aLinkOperationTuple)**

**String generateLinkOperationTupleElement(LinkOperationTupleElement aLinkOperationTupleElement)**

**String generateLinkOperationKind(LinkOperationKind aLinkOperationKind)**

**String generateSequenceOperationExpression(SequenceOperationExpression aSequenceOperationExpression)**

**String generateSequenceReductionExpression(SequenceReductionExpression aSequenceReductionExpression)**

**String generateSequenceExpansionExpression(SequenceExpansionExpression aSequenceExpansionExpression)**

**String generateClassExtentExpression(ClassExtentExpression aClassExtentExpression)**

**String generateLocalNameDeclarationStatement(LocalNameDeclarationStatement aLocalNameDeclarationStatement)**

**String generateNameExpression(NameExpression aNameExpression, Boolean isNotNew)**

.. Athena_AlfGenerator::

Athena_AlfGenerator
*******************

Specialized Alf generator to translate Alf bloc to Athena code. It inherit from :ref:`AlfGenerator <AlfGenerator>`.

*protected*

**String generateAlfBlock(Block bloc)**
   
**String generateStatement(Statement aStatement)**
   
**String generateIfStatement(IfStatement aIfStatement)**
   
**String generateSequentialClausesTemplate(SequentialClauses aSequentialClauses)**

**String generateConcurrentClausesTemplate(ConcurrentClauses aConcurrentClauses)**
   
**String generateNonFinalClauseTemplate(NonFinalClause aNonFinalClause)**
   
**String generateWhileStatement(WhileStatement aWhileStatement)**
   
**String generateInvocationOrAssignementOrDeclarationStatement(InvocationOrAssignementOrDeclarationStatement aInvocationOrAssignementOrDeclarationStatement)**
   
**String generateVariableDeclarationCompletion(VariableDeclarationCompletion aVariableDeclarationCompletion)**
   
**String generateLocalNameDeclarationStatement(LocalNameDeclarationStatement aLocalNameDeclarationStatement)**
   
**String generateNameExpression(NameExpression aNameExpression, Boolean isNotNew)**

.. CPP_AlfGenerator::

CPP_AlfGenerator
****************

Specialized Alf generator to translate Alfbloc to C++ code.  It inherit from :ref:`AlfGenerator <AlfGenerator>`.

*public*

**CPP_AlfGenerator()**

*protected*

**String generateAlfBlock(Block bloc)**
   
**String generateStatement(Statement aStatement)**
   
**String generateInlineStatement(InlineStatement aInLineStatement)**
   
**String generateIfStatement(IfStatement aIfStatement)**
   
**String generateSequentialClausesTemplate(SequentialClauses aSequentialClauses)**
   
**String generateConcurrentClausesTemplate(ConcurrentClauses aConcurrentClauses)**
   
**String generateNonFinalClauseTemplate(NonFinalClause aNonFinalClause)**
   
**String generateSwitchStatement(SwitchStatement aSwitchStatement)**
   
**String generateSwitchDefaultclause(SwitchDefaultClause aSwitchDefaultClause)**
   
**String generateSwitchClause(SwitchClause aSwitchClause)**
   
**String generateSwitchCase(SwitchCase aSwitchCase)**
   
**String generateWhileStatement(WhileStatement aWhileStatement)**
   
**String generateDoStatement(DoStatement aDoStatement)**
   
**String generateInvocationOrAssignementOrDeclarationStatement**
   
**String generateVariableDeclarationCompletion(VariableDeclarationCompletion aVariableDeclarationCompletion)**

**String generateSuperInvocationExpression(SuperInvocationExpression aSuperInvocationExpression)**
   
**String generateOperationCallExpressionWithoutDot(OperationCallExpressionWithoutDot aOperationCallExpressionWithoutDot)**
   
**String generateThisExpression(ThisExpression aThisExpression)**
   
**String generateInstanceCreationExpression(InstanceCreationExpression aInstanceCreationExpression)**
   
**String generateQualifiedNameWithBinding(QualifiedNameWithBinding aQualifiedNameWithBinding)**
   
**String generateLocalNameDeclarationStatement(LocalNameDeclarationStatement aLocalNameDeclarationStatement)**
   
**String generateNameExpression(NameExpression aNameExpression, Boolean isNotNew)**
   
} 




How to use an existing Alf generator
####################################

You can use an Alf generator in you :term`RobotML<robotml>` generator development.
You have two solution to call an existing Alf generator. But that depend how you develop your :term:`RobotML<robotml>` generator.
* If you use :term:`OCL<ocl>` template, you should to import the AlfServices into your template.Then call "createAlfBloc" to get an Alf bloc corresponding to your operation body, and call the right operation translation you need.
* If you use Java class, you should to refrence the Alf generator API, and call the static metohds "createAlfBloc" and the translation operation.


 



 


 