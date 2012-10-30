.. _Alf_Gen_API :

=====================
The Alf Generator API
=====================

In RobotML, the :term:`Alf<alf>` language is used to describe the operation contents (only OpaqueBehavior). This language permit to have a generic modeling and generate it easily in more other langauge.  

For your needs, you can create a specific :term:`Alf<alf>` generator language on using this :ref:`Alf Generator API<_Alf_Gen_API>`.

.. warning:: The :term:`Alf<alf>` knowkedge is clearly recommended. Go to see the `Alf language site <http://www.omg.com/>`_ before start your work!
 
Overview
########

.. image:: ../ATK_Scenario_images/Alf_overview.png
   :align: center
   :alt: Alf API overview.]
   
   
.. _AlfServcies:

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

.. _AlfBlock:

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

.. _IAlfGenerator:

IAlfGenerator
*************

Alf generator interface, contains the mandatory method to implement for the Alf generator.

*public*

**abstract void generate(AlfBlock bloc)**

   +-----------+------------------------+
   | bloc      | Alf bloc to translate. |
   +-----------+------------------------+
   
Abstract method to redefine in implementation. Translate the Alf bloc.

.. _AlfGenerator:

AlfGenerator
************

Abstract Alf base generator. Contains the common method for all Alf generators. It implement the IAlfGenerator_ interface.

*public*

**abstract void generate(AlfBlock bloc)**

   +-----------+------------------------+
   | bloc      | Alf bloc to translate. |
   +-----------+------------------------+
   
Translate the Alf bloc.

*protected*

.. _AlfGenerator.generateAlfBlock:

**String generateAlfBlock(org.eclipse.papyrus.uml.alf.alf.Block bloc)**

   +-----------+------------------------+
   | bloc      | Alf bloc to translate. |
   +-----------+------------------------+
   | return    | Alf bloc translation.  |
   +-----------+------------------------+

Return the Alf bloc translation.   

**String generateStatementSequence(org.eclipse.papyrus.uml.alf.alf.StatementSequence aStatementSequence)**

   +--------------------+--------------------------------------+
   | aStatementSequence | Alf statement sequence to translate. |
   +--------------------+--------------------------------------+
   | return             | Alf statement sequance translation.  |
   +--------------------+--------------------------------------+

Return the Alf statement sequence translation.

**String generateDocumentedStatement(org.eclipse.papyrus.uml.alf.alf.DocumentedStatement aDocumentedStatement)**

   +----------------------+---------------------------------------+
   | aDocumentedStatement | Alf documented statment to translate. |
   +----------------------+---------------------------------------+
   | return               | Alf documented statment translation.  |
   +----------------------+---------------------------------------+

Return the Alf documeneted statment translation.

**String generateSequoclenceStatement(org.eclipse.papyrus.uml.alf.alf.Statement aStatement)**

   +----------------------+----------------------------+
   | aStatement           | Alf statment to translate. |
   +----------------------+----------------------------+
   | return               | Alf statment translation.  |
   +----------------------+----------------------------+

Return the Alf documeneted statment translation.

.. _AlfGenerator.generateStatement:

**String generateStatement(org.eclipse.papyrus.uml.alf.alf.Statement aStatement)**

   +----------------------+----------------------------+
   | aStatement           | Alf statment to translate. |
   +----------------------+----------------------------+
   | return               | Alf statment translation.  |
   +----------------------+----------------------------+

Return the Alf documeneted statment translation.

.. _AlfGenerator.generateInlineStatement:

**String generateInlineStatement(org.eclipse.papyrus.uml.alf.alf.InlineStatement aInlineStatement)**

   +----------------------+-----------------------------------+
   | aInLineStatement     | Alf inline statment to translate. |
   +----------------------+-----------------------------------+
   | return               | Alf inline statment translation.  |
   +----------------------+-----------------------------------+

Return the Alf inline statment translation.
   
**String generateAnnotatedStatement(org.eclipse.papyrus.uml.alf.alf.AnnotatedStatement aAnnotatedStatement)***

   +----------------------+--------------------------------------+
   | aAnnotatedStatement  | Alf annotated statment to translate. |
   +----------------------+--------------------------------------+
   | return               | Alf annotated statment translation.  |
   +----------------------+--------------------------------------+

Return the Alf annotated statment translation.

**String generateBlockStatement(org.eclipse.papyrus.uml.alf.alf.BlockStatement aBlockStatement)**

   +----------------------+----------------------------------+
   | aBlockStatement      | Alf block statment to translate. |
   +----------------------+----------------------------------+
   | return               | Alf block statment translation.  |
   +----------------------+----------------------------------+

Return the Alf block statment translation.

**String generateEmptyStatement(org.eclipse.papyrus.uml.alf.alf.EmptyStatement aEmptyStatement)**
   
   +----------------------+----------------------------------+
   | aEmptyStatement      | Alf empty statment to translate. |
   +----------------------+----------------------------------+
   | return               | Alf empty statment translation.  |
   +----------------------+----------------------------------+

Return the Alf empty statment translation.

.. _AlfGenerator.generateIfStatement:

**String generateIfStatement(org.eclipse.papyrus.uml.alf.alf.IfStatement aIfStatement)**

   +----------------------+-------------------------------+
   | aIfStatement         | Alf if statment to translate. |
   +----------------------+-------------------------------+
   | return               | Alf if statment translation.  |
   +----------------------+-------------------------------+

Return the Alf if statment translation.

.. _AlfGenerator.generateSequentialClausesTemplate:

**String generateSequentialClausesTemplate(org.eclipse.papyrus.uml.alf.alf.SequentialClauses aSequentialClauses)**
   
   +----------------------+--------------------------------------+
   | aSequentialClauses   | Alf sequential clauses to translate. |
   +----------------------+--------------------------------------+
   | return               | Alf sequential clauses translation.  |
   +----------------------+--------------------------------------+

Return the Alf sequential clauses translation.

.. _AlfGenerator.generateConcurrentClausesTemplate:

**String generateConcurrentClausesTemplate(org.eclipse.papyrus.uml.alf.alf.ConcurrentClauses aConcurrentClauses)**

   +----------------------+--------------------------------------+
   | aConcurrentClauses   | Alf concurrent clauses to translate. |
   +----------------------+--------------------------------------+
   | return               | Alf concurrent clauses translation.  |
   +----------------------+--------------------------------------+

Return the Alf concurrent clauses translation.

.. _AlfGenerator.generateNonFinalClauseTemplate:

**String generateNonFinalClauseTemplate(org.eclipse.papyrus.uml.alf.alf.NonFinalClause aNonFinalClause)**

   +----------------------+------------------------------------+
   | aNonFinalClause      | Alf non final clause to translate. |
   +----------------------+------------------------------------+
   | return               | Alf non final clause translation.  |
   +----------------------+------------------------------------+

Return the Alf non final clause translation.

**String generateFinalClauseTemplate(org.eclipse.papyrus.uml.alf.alf.FinalClause aFinalClause)**

   +----------------------+--------------------------------+
   | aFianalClause        | Alf final clause to translate. |
   +----------------------+--------------------------------+
   | return               | Alf final clause translation.  |
   +----------------------+--------------------------------+

Return the Alf fianl clause translation.

.. _AlfGenerator.generateSwitchStatement:

**String generateSwitchStatement(org.eclipse.papyrus.uml.alf.alf.SwitchStatement aSwitchStatement)**

   +----------------------+------------------------------------+
   | aSwitchStatement     | Alf switch statement to translate. |
   +----------------------+------------------------------------+
   | return               | Alf switch statement translation.  |
   +----------------------+------------------------------------+

Return the Alf switch statement translation.

.. _AlfGenerator.generateSwitchDefaultclause:

**String generateSwitchDefaultclause(org.eclipse.papyrus.uml.alf.alf.SwitchDefaultClause aSwitchDefaultClause)**

   +----------------------+-----------------------------------------+
   | aSwitchDefaultClause | Alf switch default clause to translate. |
   +----------------------+-----------------------------------------+
   | return               | Alf switch default clause translation.  |
   +----------------------+-----------------------------------------+

Return the Alf switch default clause translation.

.. _AlfGenerator.generateSwitchClause:

**String generateSwitchClause(org.eclipse.papyrus.uml.alf.alf.SwitchClause aSwitchClause)**

   +----------------------+---------------------------------+
   | aSwitchClause        | Alf switch clause to translate. |
   +----------------------+---------------------------------+
   | return               | Alf switch clause translation.  |
   +----------------------+---------------------------------+

Return the Alf switch clause translation.

.. _AlfGenerator.generateSwitchCase:

**String generateSwitchCase(org.eclipse.papyrus.uml.alf.alf.SwitchCase aSwitchCase)**

   +----------------------+-------------------------------+
   | aSwitchCase          | Alf switch case to translate. |
   +----------------------+-------------------------------+
   | return               | Alf switch case translation.  |
   +----------------------+-------------------------------+

Return the Alf switch case translation.

**String generateNonEmptyStatementSequence(org.eclipse.papyrus.uml.alf.alf.NonEmptyStatementSequence aNonEmptyStatementSequence)**

   +----------------------------+------------------------------------------------+
   | anonEmptyStatementSequence | Alf non empty statement sequence to translate. |
   +----------------------------+------------------------------------------------+
   | return                     | Alf non empty statement sequence translation.  |
   +----------------------------+------------------------------------------------+

Return the Alf non empty statement sequence translation.

.. _AlfGenerator.generateWhileStatement:

**String generateWhileStatement(org.eclipse.papyrus.uml.alf.alf.WhileStatement aWhileStatement)**

   +----------------------+-----------------------------------+
   | aWhileStatement      | Alf while statement to translate. |
   +----------------------+-----------------------------------+
   | return               | Alf while statement translation.  |
   +----------------------+-----------------------------------+

Return the Alf while statement translation.

.. _AlfGenerator.generateDoStatement:

**String generateDoStatement(org.eclipse.papyrus.uml.alf.alf.DoStatement aDoStatement)**

   +----------------------+--------------------------------+
   | aDoStatement         | Alf do statement to translate. |
   +----------------------+--------------------------------+
   | return               | Alf do statement translation.  |
   +----------------------+--------------------------------+

Return the Alf do statement translation.

**String generateForStatement(org.eclipse.papyrus.uml.alf.alf.ForStatement aForStatement)**

   +----------------------+---------------------------------+
   | aForStatement        | Alf for statement to translate. |
   +----------------------+---------------------------------+
   | return               | Alf for statement translation.  |
   +----------------------+---------------------------------+

Return the Alf for statement translation.

**String generateBreakStatement(org.eclipse.papyrus.uml.alf.alf.BreakStatement aBreakStatement)**

   +----------------------+-----------------------------------+
   | aBreakStatement      | Alf break statement to translate. |
   +----------------------+-----------------------------------+
   | return               | Alf break statement translation.  |
   +----------------------+-----------------------------------+

Return the Alf break statement translation.

**String generateReturnStatement(org.eclipse.papyrus.uml.alf.alf.ReturnStatement aReturnStatement)**

   +----------------------+------------------------------------+
   | aReturnStatement     | Alf return statement to translate. |
   +----------------------+------------------------------------+
   | return               | Alf return statement translation.  |
   +----------------------+------------------------------------+

Return the Alf return statement translation.

**String generateAcceptStatement(org.eclipse.papyrus.uml.alf.alf.AcceptStatement aAcceptStatement)**

   +----------------------+------------------------------------+
   | aAcceptStatement     | Alf accept statement to translate. |
   +----------------------+------------------------------------+
   | return               | Alf accepet statement translation. |
   +----------------------+------------------------------------+

Return the Alf accept statement translation.

**String generateClassifyStatement(org.eclipse.papyrus.uml.alf.alf.ClassifyStatement aClassifyStatement)**

   +----------------------+--------------------------------------+
   | aClassifyStatement   | Alf classify statement to translate. |
   +----------------------+--------------------------------------+
   | return               | Alf classify statement translation.  |
   +----------------------+--------------------------------------+

Return the Alf classify statement translation.

.. _AlfGenerator.generateInvocationOrAssignementOrDeclarationStatement:

**String generateInvocationOrAssignementOrDeclarationStatement(org.eclipse.papyrus.uml.alf.alf.InvocationOrAssignementOrDeclarationStatement aInvocationOrAssignementOrDeclarationStatement)**

   +------------------------------------------------+----------------------------------------------------------------------+
   | aInvocationorAssignementOrDeclarationStatement | Alf invocation or assignement or declaration statement to translate. |
   +------------------------------------------------+----------------------------------------------------------------------+
   | return                                         | Alf invocation or assignement or declaration statement translation.  |
   +------------------------------------------------+----------------------------------------------------------------------+

Return the Alf  invocation, or assignement, or declaration, statement translation.

.. _AlfGenerator.generateVariableDeclarationCompletion:

**String generateVariableDeclarationCompletion(org.eclipse.papyrus.uml.alf.alf.VariableDeclarationCompletion aVariableDeclarationCompletion)**

   +--------------------------------+---------------------------------------------------+
   | aVaraibleDeclarationCompletion | Alf variable declaration completion to translate. |
   +--------------------------------+---------------------------------------------------+
   | return                         | Alf variable declaration completion translation.  |
   +--------------------------------+---------------------------------------------------+

Return the Alf variable declaration completion  translation.

**String generateAssignmentCompletion(org.eclipse.papyrus.uml.alf.alf.AssignmentCompletion aAssignmentCompletion)**

   +------------------------+------------------------------------------+
   | aAssignementCompletion | Alf assignement completion to translate. |
   +------------------------+------------------------------------------+
   | return                 | Alf assignement completion translation.  |
   +------------------------+------------------------------------------+

Return the Alf assignement completion translation.

**String generateAssignmentOperator(org.eclipse.papyrus.uml.alf.alf.AssignmentOperator aAssignmentOperator)**

   +----------------------+----------------------------------------+
   | aAssignementOperator | Alf assignement operator to translate. |
   +----------------------+----------------------------------------+
   | return               | Alf assignement operator translation.  |
   +----------------------+----------------------------------------+

Return the Alf assignement operator translation.

**String generateSuperInvocationStatement(org.eclipse.papyrus.uml.alf.alf.SuperInvocationStatement aSuperInvocationStatement)**

   +---------------------------+----------------------------------------------+
   | aSuperInvocationStatement | Alf super invocation statement to translate. |
   +---------------------------+----------------------------------------------+
   | return                    | Alf super invocation translation.            |
   +---------------------------+----------------------------------------------+

Return the Alf super invocation statement translation.

.. _AlfGenerator.generateSuperInvocationExpression:

**String generateSuperInvocationExpression(org.eclipse.papyrus.uml.alf.alf.SuperInvocationExpression aSuperInvocationExpression)**

   +----------------------------+-----------------------------------------------+
   | aSuperInvocationExpression | Alf super invocation expression to translate. |
   +----------------------------+-----------------------------------------------+
   | return                     | Alf super invocation expression translation.  |
   +----------------------------+-----------------------------------------------+

Return the Alf super invocation expression translation.

**String generateOperationCallExpression(org.eclipse.papyrus.uml.alf.alf.OperationCallExpression aOperationCallExpression)**

   +--------------------------+---------------------------------------------+
   | aOperationCallExpression | Alf operation call expression to translate. |
   +--------------------------+---------------------------------------------+
   | return                   | Alf operation call expression translation.  |
   +--------------------------+---------------------------------------------+

Return the Alf operation call expression translation.

**String generateTupleTemplate(org.eclipse.papyrus.uml.alf.alf.Tuple aTuple)**

   +----------+-------------------------+
   | aTuple   | Alf tuple to translate. |
   +----------+-------------------------+
   | return   | Alf tuple translation.  |
   +----------+-------------------------+

Return the Alf tuple translation.
   
**String generateTupleElement(org.eclipse.papyrus.uml.alf.alf.TupleElement aTupleElement)**

   +---------------+---------------------------------+
   | aTupleElement | Alf tuple element to translate. |
   +---------------+---------------------------------+
   | return        | Alf tuple element translation.  |
   +---------------+---------------------------------+

Return the Alf tuple element translation.

.. _AlfGenerator.generateOperationCallExpressionWithoutDot:

**String generateOperationCallExpressionWithoutDot(org.eclipse.papyrus.uml.alf.alf.OperationCallExpressionWithoutDot aOperationCallExpressionWithoutDot)**

   +------------------------------------+---------------------------------------------------------+
   | aOperationCallExpressionWithoutDot | Alf operation call expression without dot to translate. |
   +------------------------------------+---------------------------------------------------------+
   | return                             | Alf operation call expression without dot translation.  |
   +------------------------------------+---------------------------------------------------------+

Return the Alf operation call expression without dot translation.

**String generateThisInvocationStatement(org.eclipse.papyrus.uml.alf.alf.ThisInvocationStatement aThisInvocationStatement)**

   +--------------------------+---------------------------------------------+
   | aThisInvocationstatement | Alf this invocation statement to translate. |
   +--------------------------+---------------------------------------------+
   | return                   | Alf this invocation statement translation.  |
   +--------------------------+---------------------------------------------+

Return the Alf this invocation statement translation.

**String generateInstanceCreationInvocationStatement(org.eclipse.papyrus.uml.alf.alf.InstanceCreationInvocationStatement aInstanceCreationInvocationStatement)**

   +--------------------------------------+----------------------------------------------------------+
   | aInstanceCreationinvocationStatement | Alf instance creation invocation statement to translate. |
   +--------------------------------------+----------------------------------------------------------+
   | return                               | Alf instance creation invocation statement translation.  |
   +--------------------------------------+----------------------------------------------------------+

Return the Alf instance creation invocation statement translation.

**String generateAnnotation(org.eclipse.papyrus.uml.alf.alf.Annotation aAnnotation)**

   +-------------+------------------------------+
   | aAnnotation | Alf annotation to translate. |
   +-------------+------------------------------+
   | return      | Alf annotation translation.  |
   +-------------+------------------------------+

Return the Alf annotation translation.

**String generateExpressionForm(org.eclipse.papyrus.uml.alf.alf.Expression aExpression)**

   +-------------+------------------------------+
   | aExpression | Alf expression to translate. |
   +-------------+------------------------------+
   | return      | Alf expression translation.  |
   +-------------+------------------------------+

Return the Alf expression translation.

**String generateSequenceExpressionForm(org.eclipse.papyrus.uml.alf.alf.EList<Expression> list)**

   +-------------+------------------------------+
   | list   | Alf expression list to translate. |
   +-------------+------------------------------+
   | return | Alf expression list translation.  |
   +-------------+------------------------------+

Return the Alf expression list translation.

**String generateConditionalTestExpression(org.eclipse.papyrus.uml.alf.alf.ConditionalTestExpression aConditionalTestExpression)**

   +----------------------------+-----------------------------------------------+
   | aConditionalTestExpression | Alf conditional test expression to translate. |
   +----------------------------+-----------------------------------------------+
   | return                     | Alf conditionnal test expression translation. |
   +----------------------------+-----------------------------------------------+

Return the Alf conditonal test expression translation.

**String generateConditionalOrExpression(org.eclipse.papyrus.uml.alf.alf.ConditionalOrExpression aConditionalOrExpression)**

   +--------------------------+---------------------------------------------+
   | aConditionalOrExpression | Alf conditional or expression to translate. |
   +--------------------------+---------------------------------------------+
   | return                   | Alf conditionnal or expression translation. |
   +--------------------------+---------------------------------------------+

Return the Alf conditonal or expression translation.
   
**String generateConditionalAndExpression(org.eclipse.papyrus.uml.alf.alf.ConditionalAndExpression aConditionalAndExpression)**

   +---------------------------+----------------------------------------------+
   | aConditionalAndExpression | Alf conditional and expression to translate. |
   +---------------------------+----------------------------------------------+
   | return                    | Alf conditionnal and expression translation. |
   +---------------------------+----------------------------------------------+

Return the Alf conditonal and expression translation.

**String generateInclusiveOrExpression(org.eclipse.papyrus.uml.alf.alf.InclusiveOrExpression aInclusiveOrExpression)**

   +------------------------+-------------------------------------------+
   | aInclusiveOrExpression | Alf inclusive or expression to translate. |
   +------------------------+-------------------------------------------+
   | return                 | Alf inclusive or expression translation.  |
   +------------------------+-------------------------------------------+

Return the Alf inclusive or expression translation.

**String generateExclusiveOrExpression(org.eclipse.papyrus.uml.alf.alf.ExclusiveOrExpression aExclusiveOrExpression)**

   +------------------------+-------------------------------------------+
   | aExclusiveOrExpression | Alf exclusive or expression to translate. |
   +------------------------+-------------------------------------------+
   | return                 | Alf exclusive or expression translation.  |
   +------------------------+-------------------------------------------+

Return the Alf exclusive or expression translation.

**String generateAndExpression(org.eclipse.papyrus.uml.alf.alf.AndExpression aAndExpression)**
   
   +----------------+----------------------------------+
   | aAndExpression | Alf and expression to translate. |
   +----------------+----------------------------------+
   | return         | Alf and expression translation.  |
   +----------------+----------------------------------+

Return the Alf conditonal test expression translation.

**String generateEqualityExpression(org.eclipse.papyrus.uml.alf.alf.EqualityExpression aEqualityExpression)**

   +---------------------+---------------------------------------+
   | aEqualityExpression | Alf equality expression to translate. |
   +---------------------+---------------------------------------+
   | return              | Alf equality expression translation.  |
   +---------------------+---------------------------------------+

Return the Alf equality expression translation.

**String generateClassificationExpression(org.eclipse.papyrus.uml.alf.alf.ClassificationExpression aClassificationExpression)**

   +---------------------------+---------------------------------------------+
   | aClassificationExpression | Alf classification expression to translate. |
   +---------------------------+---------------------------------------------+
   | return                    | Alf classification expression translation.  |
   +---------------------------+---------------------------------------------+

Return the Alf classifcation expression translation.

**String generateSequenceConstructionOrAccessCompletion(org.eclipse.papyrus.uml.alf.alf.SequenceConstructionOrAccessCompletion aSequenceConstructionOrAccessCompletion)**

   +----------------------------------------+----------------------------------------------------------------+
   | aSequenceContructionOrAccessCompletion | Alf sequence construction, or access completion  to translate. |
   +----------------------------------------+----------------------------------------------------------------+
   | return                                 | Alf sequence construction, or access completion  translation.  |
   +----------------------------------------+----------------------------------------------------------------+

Return the Alf sequence construction, or access completion  translation.

**String generateQualifiedNamePath(org.eclipse.papyrus.uml.alf.alf.QualifiedNamePath aQualifiedNamePath)**

   +--------------------+---------------------------------------+
   | aQualifiedNamePath | Alf qualified name path to translate. |
   +--------------------+---------------------------------------+
   | return             | Alf qualified name path translation.  |
   +--------------------+---------------------------------------+

Return the Alf qualified name path translation.

**String generateUnqualifiedName(org.eclipse.papyrus.uml.alf.alf.UnqualifiedName aUnqualifiedName)**

   +------------------+------------------------------------+
   | aUnqualifiedName | Alf unqualified name to translate. |
   +------------------+------------------------------------+
   | return           | Alf unqualified name translation.  |
   +------------------+------------------------------------+

Return the Alf unqualified name  translation.

**String generateTemplateBinding(org.eclipse.papyrus.uml.alf.alf.TemplateBinding aTemplateBinding)**

   +------------------+------------------------------------+
   | aTemplateBinding | Alf template binding to translate. |
   +------------------+------------------------------------+
   | return           | Alf template binding translation.  |
   +------------------+------------------------------------+

Return the Alf template binding translation.

**String generateRelationalExpression(org.eclipse.papyrus.uml.alf.alf.RelationalExpression aRelationalExpression)**

   +------------------------+-----------------------------------------+
   | aRelationnalExpression | Alf relational expression to translate. |
   +------------------------+-----------------------------------------+
   | return                 | Alf relationnal expression translation. |
   +------------------------+-----------------------------------------+

Return the Alf relational expression translation.

**String generateShiftExpression(org.eclipse.papyrus.uml.alf.alf.ShiftExpression aShiftExpression)**

   +------------------+------------------------------------+
   | aShiftExpression | Alf shift expression to translate. |
   +------------------+------------------------------------+
   | return           | Alf shift expression translation.  |
   +------------------+------------------------------------+

Return the Alf shift expression translation.

**String generateAdditiveExpression(org.eclipse.papyrus.uml.alf.alf.AdditiveExpression aAdditiveExpression)**

   +---------------------+---------------------------------------+
   | aAdditiveExpression | Alf additive expression to translate. |
   +---------------------+---------------------------------------+
   | return              | Alf additive expression translation.  |
   +---------------------+---------------------------------------+

Return the Alf additive expression translation.
   
**String generateMultiplicativeExpression(org.eclipse.papyrus.uml.alf.alf.MultiplicativeExpression aMultiplicativeExpression)**

   +---------------------------+---------------------------------------------+
   | aMultiplicativeExpression | Alf multiplicative expression to translate. |
   +---------------------------+---------------------------------------------+
   | return                    | Alf multiplicative expression translation.  |
   +---------------------------+---------------------------------------------+

Return the Alf multiplicative expression translation.

**String generateUnaryExpression(org.eclipse.papyrus.uml.alf.alf.UnaryExpression aUnaryExpression)**

   +------------------+------------------------------------+
   | aUnaryExpression | Alf unary expression to translate. |
   +------------------+------------------------------------+
   | return           | Alf unary expression translation.  |
   +------------------+------------------------------------+

Return the Alf unary expression translation.

**String generatePrimaryExpression(org.eclipse.papyrus.uml.alf.alf.PrimaryExpression aPrimaryExpression)**

   +--------------------+--------------------------------------+
   | aPrimaryExpression | Alf primary expression to translate. |
   +--------------------+--------------------------------------+
   | return             | Alf primary expression translation.  |
   +--------------------+--------------------------------------+

Return the Alf primary expression translation.

**String generateValueSpecification(org.eclipse.papyrus.uml.alf.alf.ValueSpecification aValueSpecification)**

   +---------------------+---------------------------------------+
   | aValueSpecification | Alf value specification to translate. |
   +---------------------+---------------------------------------+
   | return              | Alf value secification translation.   |
   +---------------------+---------------------------------------+

Return the Alf value specification translation.

.. _Algenerator.generateThisExpression:

**String generateThisExpression(org.eclipse.papyrus.uml.alf.alf.ThisExpression aThisExpression)**

   +-----------------+-----------------------------------+
   | aThisExpression | Alf this expression to translate. |
   +-----------------+-----------------------------------+
   | return          | Alf this expression translation.  |
   +-----------------+-----------------------------------+

Return the Alf this expression translation.

**String generateNullExpression(org.eclipse.papyrus.uml.alf.alf.NullExpression aNullExpression)**

   +-----------------+-----------------------------------+
   | aNullExpression | Alf null expression to translate. |
   +-----------------+-----------------------------------+
   | return          | Alf null expression translation.  |
   +-----------------+-----------------------------------+

Return the Alf null expression translation.

**String generateParenthesizedExpression(org.eclipse.papyrus.uml.alf.alf.ParenthesizedExpression aParenthesizedExpression)**

   +--------------------------+-------------------------------------------+
   | aParenthesizedExpression | Alf parenthesizedExpression to translate. |
   +--------------------------+-------------------------------------------+
   | return                   | Alf parenthsized expression translation.  |
   +--------------------------+-------------------------------------------+

Return the Alf parenthesized expression translation.

**String generateNonLiteralValueSpecification(org.eclipse.papyrus.uml.alf.alf.NonLiteralValueSpecification aNonLiteralValueSpecification)**

   +-------------------------------+---------------------------------------------------+
   | aNonLiteralValueSpecification | Alf non literal value specification to translate. |
   +-------------------------------+---------------------------------------------------+
   | return                        | Alf non literal value specification translation.  |
   +-------------------------------+---------------------------------------------------+

Return the Alf non literal value specification translation.

.. _AlfGenerator.generateInstanceCreationExpression:

**String generateInstanceCreationExpression(org.eclipse.papyrus.uml.alf.alf.InstanceCreationExpression aInstanceCreationExpression)**

   +------------------------------+------------------------------------------------+
   | aInstanceCreationExpressionn | Alf instance creation expression to translate. |
   +------------------------------+------------------------------------------------+
   | return                       | Alf instance creation expression translation.  |
   +------------------------------+------------------------------------------------+

Return the Alf instance creation expression translation.

.. _AlfGenerator.generateQualifiedNameWithBinding:

**String generateQualifiedNameWithBinding(org.eclipse.papyrus.uml.alf.alf.QualifiedNameWithBinding aQualifiedNameWithBinding)**

   +---------------------------+-----------------------------------------------+
   | aQualifiedNameWithBinding | Alf qualified name with binding to translate. |
   +---------------------------+-----------------------------------------------+
   | return                    | Alf qualified name with binding translation.  |
   +---------------------------+-----------------------------------------------+

Return the Alf qualified name with binding translation.
   
**String generateSequenceConstructionCompletion(org.eclipse.papyrus.uml.alf.alf.SequenceConstructionCompletion aSequenceConstructionCompletion)**

   +--------------------------------+----------------------------------------------------+
   | aSequenceContructionCompletion | Alf sequence construction completion to translate. |
   +--------------------------------+----------------------------------------------------+
   | return                         | Alf sequence construction completion translation.  |
   +--------------------------------+----------------------------------------------------+

Return the Alf sequence construction completion translation.

**String generateLiteral(org.eclipse.papyrus.uml.alf.alf.LITERAL aLITERAL)**

   +----------+---------------------------+
   | aLITERAL | Alf literal to translate. |
   +----------+---------------------------+
   | return   | Alf literal translation.  |
   +----------+---------------------------+

Return the Alf literal translation.

**String generateIntegerLiteral(org.eclipse.papyrus.uml.alf.alf.INTEGER_LITERAL aINTEGER_LITERAL)**

   +------------------+-----------------------------------+
   | aINTEGER_LITERAL | Alf integer literal to translate. |
   +------------------+-----------------------------------+
   | return           | Alf integer literal translation.  |
   +------------------+-----------------------------------+

Return the Alf integer literal translation.

**String generateStringLiteral(org.eclipse.papyrus.uml.alf.alf.STRING_LITERAL aSTRING_LITERAL)**

   +------------------+----------------------------------+
   | aSTRING_LITERAL  | Alf string literal to translate. |
   +------------------+----------------------------------+
   | return           | Alf string literal translation.  |
   +------------------+----------------------------------+

Return the Alf string literal translation.

**String generateBooleanLiteral(org.eclipse.papyrus.uml.alf.alf.BOOLEAN_LITERAL aBOOLEAN_LITERAL)**

   +------------------+-----------------------------------+
   | aBOOLEAN_LITERAL | Alf boolean literal to translate. |
   +------------------+-----------------------------------+
   | return           | Alf boolean literal translation.  |
   +------------------+-----------------------------------+

Return the Alf boolean literal translation.

**String generateNumberLiteral(org.eclipse.papyrus.uml.alf.alf.NUMBER_LITERAL aNUMBER_LITERAL)**

   +-----------------+----------------------------------+
   | aNUMBER_LITERAL | Alf number literal to translate. |
   +-----------------+----------------------------------+
   | return          | Alf number literal translation.  |
   +-----------------+----------------------------------+

Return the Alf number literal translation.

**String generateUnlimitedLiteral(org.eclipse.papyrus.uml.alf.alf.UNLIMITED_LITERAL aUNLIMITED_LITERAL)**

   +--------------------+-------------------------------------+
   | aUNLIMITED_LITERAL | Alf unlimited literal to translate. |
   +--------------------+-------------------------------------+
   | return             | Alf unlimited literal translation.  |
   +--------------------+-------------------------------------+

Return the Alf unlimited literal translation.

**String generateSuffixExpression(org.eclipse.papyrus.uml.alf.alf.SuffixExpression aSuffixExpression, String dot_or_arrow)**

   +-------------------+------------------------------------+
   | aSuffixExpression | Alf suffix expression to translate |
   +-------------------+------------------------------------+
   | dot_or_arrow      | Suffix.                            |
   +-------------------+------------------------------------+
   | return            | Alf suffix expression translation. |
   +-------------------+------------------------------------+

Return the Alf suffix expression translation.

**String generatePropertyCallExpression(org.eclipse.papyrus.uml.alf.alf.PropertyCallExpression aPropertyCallExpression)**
 
   +-------------------------+--------------------------------------------+
   | aPropertyCallExpression | Alf property call expression to translate. |
   +-------------------------+--------------------------------------------+
   | return                  | Alf property call expression translation.  |
   +-------------------------+--------------------------------------------+

Return the Alf property call expression translation.

**String generateLinkOperationExpression(org.eclipse.papyrus.uml.alf.alf.LinkOperationExpression aLinkOperationExpression)**

   +--------------------------+---------------------------------------------+
   | aLinkOperationExpression | Alf link operation expression to translate. |
   +--------------------------+---------------------------------------------+
   | return                   | Alf link operation expression translation.  |
   +--------------------------+---------------------------------------------+

Return the Alf link operation expression  translation.

**String generateLinkOperationTuple(org.eclipse.papyrus.uml.alf.alf.LinkOperationTuple aLinkOperationTuple)**

   +----------------------+----------------------------------------+
   | aLinkOperationTuple  | Alf link operation tuple to translate. |
   +----------------------+----------------------------------------+
   | return               | Alf link operation tuple translation.  |
   +----------------------+----------------------------------------+

Return the Alf link operation tuple translation.

**String generateLinkOperationTupleElement(org.eclipse.papyrus.uml.alf.alf.LinkOperationTupleElement aLinkOperationTupleElement)**

   +----------------------------+------------------------------------------------+
   | aLinkOperationTupleElement | Alf link operation tuple element to translate. |
   +----------------------------+------------------------------------------------+
   | return                     | Alf link operation tuple element translation.  |
   +----------------------------+------------------------------------------------+

Return the Alf link operation tuple element translation.

**String generateLinkOperationKind(org.eclipse.papyrus.uml.alf.alf.LinkOperationKind aLinkOperationKind)**

   +--------------------+---------------------------------------+
   | aLinkOperationKind | Alf link operation kind to translate. |
   +--------------------+---------------------------------------+
   | return             | Alf link operation kind translation.  |
   +--------------------+---------------------------------------+

Return the Alf link operation kind translation.

**String generateSequenceOperationExpression(org.eclipse.papyrus.uml.alf.alf.SequenceOperationExpression aSequenceOperationExpression)**

   +------------------------------+-------------------------------------------------+
   | aSequenceOperationExpression | Alf sequence operation expression to translate. |
   +------------------------------+-------------------------------------------------+
   | return                       | Alf sequence operation expression translation.  |
   +------------------------------+-------------------------------------------------+

Return the Alf sequence operation expression translation.

**String generateSequenceReductionExpression(org.eclipse.papyrus.uml.alf.alf.SequenceReductionExpression aSequenceReductionExpression)**

   +------------------------------+-------------------------------------------------+
   | aSequenceReductionExpression | Alf sequence reduction expression to translate. |
   +------------------------------+-------------------------------------------------+
   | return                       | Alf sequence reduction expression translation.  |
   +------------------------------+-------------------------------------------------+

Return the Alf sequence reduction expression translation.

**String generateSequenceExpansionExpression(org.eclipse.papyrus.uml.alf.alf.SequenceExpansionExpression aSequenceExpansionExpression)**

   +------------------------------+-------------------------------------------------+
   | aSequenceExpansionExpression | Alf sequence expansion expression to translate. |
   +------------------------------+-------------------------------------------------+
   | return                       | Alf sequence expansion expression translation.  |
   +------------------------------+-------------------------------------------------+

Return the Alf sequence expansion epxression translation.

**String generateClassExtentExpression(org.eclipse.papyrus.uml.alf.alf.ClassExtentExpression aClassExtentExpression)**

   +------------------------+-------------------------------------------+
   | aClassExtentExpression | Alf class extent expression to translate. |
   +------------------------+-------------------------------------------+
   | return                 | Alf class extent expression translation.  |
   +------------------------+-------------------------------------------+

Return the Alf class extent expression translation.

.. _AlfGenerator.generateLocalNameDeclarationStatement:

**String generateLocalNameDeclarationStatement(org.eclipse.papyrus.uml.alf.alf.LocalNameDeclarationStatement aLocalNameDeclarationStatement)**

   +---------------------------------+----------------------------------------------------+
   | aLocalNameDeclarartionStatement | Alf local name declaration statement to translate. |
   +---------------------------------+----------------------------------------------------+
   | return                          | Alf local name declaration statement translation.  |
   +---------------------------------+----------------------------------------------------+

Return the Alf local name declaration statement translation.

.. _AlfGenerator.generateNameExpression:

**String generateNameExpression(org.eclipse.papyrus.uml.alf.alf.NameExpression aNameExpression, Boolean isNotNew)**
   
   +-----------------+------------------------------------+
   | aNameExpression |  Alf name expression to translate. |
   +-----------------+------------------------------------+
   | isNotNew        | is a new name expression ?         |
   +-----------------+------------------------------------+
   | return          | Alf name expression translation.   |
   +-----------------+------------------------------------+

Return the Alf name expression translation.

.. _Athena_AlfGenerator:

Athena_AlfGenerator
*******************

Specialized Alf generator to translate Alf bloc to Athena code. It inherit from AlfGenerator_.

*protected*

**String generateAlfBlock(org.eclipse.papyrus.uml.alf.alf.Block bloc)**
   
   see AlfGenerator.generateAlfBlock_
   
**String generateStatement(org.eclipse.papyrus.uml.alf.alf.Statement aStatement)**

   see AlfGenerator.generateStatement_
   
**String generateIfStatement(org.eclipse.papyrus.uml.alf.alf.IfStatement aIfStatement)**

   see AlfGenerator.generateifStatement
   
**String generateSequentialClausesTemplate(org.eclipse.papyrus.uml.alf.alf.SequentialClauses aSequentialClauses)**

   see AlfGenerator.generateSequentialClausesTemplate_

**String generateConcurrentClausesTemplate(org.eclipse.papyrus.uml.alf.alf.ConcurrentClauses aConcurrentClauses)**

   see AlfGenerator.generateConcurrentClausesTemplate_
   
**String generateNonFinalClauseTemplate(org.eclipse.papyrus.uml.alf.alf.NonFinalClause aNonFinalClause)**

   see AlfGenerator.generateFinalClauseTemplate_
   
**String generateWhileStatement(org.eclipse.papyrus.uml.alf.alf.WhileStatement aWhileStatement)**

   see AlfGenerator.generateWhileStatement_
   
**String generateInvocationOrAssignementOrDeclarationStatement(org.eclipse.papyrus.uml.alf.alf.InvocationOrAssignementOrDeclarationStatement aInvocationOrAssignementOrDeclarationStatement)**

   see AlfGenerator.generateInvocationOrAssignementOrDeclarationStatement_
   
**String generateVariableDeclarationCompletion(org.eclipse.papyrus.uml.alf.alf.VariableDeclarationCompletion aVariableDeclarationCompletion)**

   see AlfGenerator.generateVariableDeclarationCompletion_
   
**String generateLocalNameDeclarationStatement(org.eclipse.papyrus.uml.alf.alf.LocalNameDeclarationStatement aLocalNameDeclarationStatement)**

   see AlfGenerator.generateLocalNameDeclarationStatement_
   
**String generateNameExpression(org.eclipse.papyrus.uml.alf.alf.NameExpression aNameExpression, Boolean isNotNew)**

   see AlfGenerator.generateNameExpression_

.. _CPP_AlfGenerator:

CPP_AlfGenerator
****************

Specialized Alf generator to translate Alfbloc to C++ code.  It inherit from AlfGenerator_.

*public*

**CPP_AlfGenerator()**

   Constrcutor
   
*protected*

**String generateAlfBlock(org.eclipse.papyrus.uml.alf.alf.Block bloc)**

   see AlfGenerator.generateAlfBlock_
   
**String generateStatement(org.eclipse.papyrus.uml.alf.alf.Statement aStatement)**

   see AlfGenerator.generateStatement_
   
**String generateInlineStatement(org.eclipse.papyrus.uml.alf.alf.InlineStatement aInLineStatement)**

   see AlfGenerator.generateInlineStatement_
   
**String generateIfStatement(org.eclipse.papyrus.uml.alf.alf.IfStatement aIfStatement)**

   see AlfGenerator.generateIfStatement_
   
**String generateSequentialClausesTemplate(org.eclipse.papyrus.uml.alf.alf.SequentialClauses aSequentialClauses)**

   see AlfGenerator.generateSequentialClausesTemplate_
   
**String generateConcurrentClausesTemplate(org.eclipse.papyrus.uml.alf.alf.ConcurrentClauses aConcurrentClauses)**

   see AlfGenerator.generateConcurrentClausesTemplate_
   
**String generateNonFinalClauseTemplate(org.eclipse.papyrus.uml.alf.alf.NonFinalClause aNonFinalClause)**

   see AlfGenerator.generateNonFinalClauseTemplate_
   
**String generateSwitchStatement(org.eclipse.papyrus.uml.alf.alf.SwitchStatement aSwitchStatement)**

   see AlfGenerator.generateSwitchStatement_
   
**String generateSwitchDefaultclause(org.eclipse.papyrus.uml.alf.alf.SwitchDefaultClause aSwitchDefaultClause)**

   see AlfGenerator.generateSwitchDefaultclause_
   
**String generateSwitchClause(org.eclipse.papyrus.uml.alf.alf.SwitchClause aSwitchClause)**

   see AlfGenerator.generateSwitchClause_
   
**String generateSwitchCase(org.eclipse.papyrus.uml.alf.alf.SwitchCase aSwitchCase)**

   see AlfGenerator.generateSwitchCase_
   
**String generateWhileStatement(org.eclipse.papyrus.uml.alf.alf.WhileStatement aWhileStatement)**

   see AlfGenerator.generateWhileStatement_
   
**String generateDoStatement(org.eclipse.papyrus.uml.alf.alf.DoStatement aDoStatement)**

   see AlfGenerator.generateDoStatement_
   
**String generateInvocationOrAssignementOrDeclarationStatement(org.eclipse.papyrus.uml.alf.alf.InvocationOrAssignementOrDeclarationStatement aInvocationOrAssignementorDeclarationStatement)**

   see AlfGenerator.generateInvocationOrAssignementOrDeclarationStatement_
   
**String generateVariableDeclarationCompletion(org.eclipse.papyrus.uml.alf.alf.VariableDeclarationCompletion aVariableDeclarationCompletion)**

   see AlfGenerator.generateVariableDeclarationCompletion_

**String generateSuperInvocationExpression(org.eclipse.papyrus.uml.alf.alf.SuperInvocationExpression aSuperInvocationExpression)**

   see AlfGenerator.generateSuperInvocationExpression_
   
**String generateOperationCallExpressionWithoutDot(org.eclipse.papyrus.uml.alf.alf.OperationCallExpressionWithoutDot aOperationCallExpressionWithoutDot)**

   see AlfGenerator.generateOperationCallExpressionWithoutDot_
   
**String generateThisExpression(org.eclipse.papyrus.uml.alf.alf.ThisExpression aThisExpression)**

   see AlfGenerator.generateThisExpression_
   
**String generateInstanceCreationExpression(org.eclipse.papyrus.uml.alf.alf.InstanceCreationExpression aInstanceCreationExpression)**

   see AlfGenerator.generateInstanceCreationExpression_
   
**String generateQualifiedNameWithBinding(org.eclipse.papyrus.uml.alf.alf.QualifiedNameWithBinding aQualifiedNameWithBinding)**

   see AlfGenerator.generateQualifiedNameWithBinding_
   
**String generateLocalNameDeclarationStatement(org.eclipse.papyrus.uml.alf.alf.LocalNameDeclarationStatement aLocalNameDeclarationStatement)**

   see AlfGenerator.generateLocalNameDeclarationStatement_
   
**String generateNameExpression(org.eclipse.papyrus.uml.alf.alf.NameExpression aNameExpression, Boolean isNotNew)**

   see AlfGenerator.generateNameExpression_

How to use an existing Alf generator
####################################

You can use an Alf generator in your :term:`RobotML<robotml>` generator development.
You have two solution to call an existing Alf generator. But that depend how you develop your :term:`RobotML<robotml>` generator.

* If you use :term:`Acceleo<acceleo>` template, you should to import the AlfServices into your template.Then call `createAlfBloc` to get an Alf bloc corresponding to your operation body, and call the right operation translation you need.

.. code-block:: ocl

   [let behavior : OpaqueBehavior = element.oclAsType(OpaqueBahevior)]
      [let bloc : alf::Block = createAlfBloc(behavior)]
         [if((bloc = null) =(false))]
            [translateAlfBlocTo_Athena(bloc)/]
          [/if]
      [/let]
   [/let]

* If you use JAVA class, you should to refrence the Alf generator API, and call the static methods `createAlfBloc` and the translation operation.

.. code-block:: java

   OpaqueBahevior behavior = (OpaqueBehavior)element;
   org.eclipse.papyrus.uml.alf.alf.Block bloc = AlfServices.createAlfBloc(behavior);
   if(bloc != null)
   {
      String result = AlfServices.translateAlfBlocTo_Athena(behavior);
   }


How to create a new Alf generator
#################################

If you use a specific language (not using in the robotml platform), you can create a new Alf generator with this API. You should do the following steps:

1. Create a new class generator `XXX_AlfGenerator`, inherited from AlfGenerator_.

.. note:: By convention your generator shouk be suffixed `AlfGenerator`.

2. Override the needing methods to specify your result language generation.

3. Modify the AlfServices_ class to lauch your generator.

.. note:: By convention your calling methods should be prefixed by `translateAlfBlocTo_`.

.. code-block:: java

   public static String translateAlfBlocTo_XXX(org.eclipse.papyrus.uml.alf.alf.Block bloc)
   {
      return AlfServices.translateAlfBloc(bloc, new XXX_AlfGenerator());
   }

4. Call your Alf generator on your source code

.. seealso:: how to use an existing Alf generator 



 


