# adapt-contrib-assessmentResultsTotal-audio  

**Assessment Results Total Audio** is an audio enabled *presentation component*.  

<img src="https://github.com/adaptlearning/documentation/blob/master/04_wiki_assets/plug-ins/images/assessmentResults01.png" alt="sample assessment results component">

It is used to display the total result of all assessment's. It can be used only in conjunction with [adapt-contrib-assessment](https://github.com/adaptlearning/adapt-contrib-assessment). Feedback and the opportunity to reattempt the assessment may be coordinated with range of scores, and most importantly, with the `_scoreToPass` variable from **Assessment**.

## Installation

This custom component must be installed manually.

## Settings Overview

**Important note: do not put the Assessment Results Total Audio component in the same article as the assessment itself**.

The attributes listed below are used in *components.json* to configure **Assessment Results Total Audio**, and are properly formatted as JSON in [*example.json*](https://github.com/deltanet/adapt-contrib-assessmentResultsTotal-audio/blob/master/example.json). Visit the [**Assessment Results Total Audio** wiki](https://github.com/deltanet/adapt-contrib-assessmentResultsTotal-audio/wiki) for more information about how they appear in the [authoring tool](https://github.com/adaptlearning/adapt_authoring/wiki).

### Attributes

[**core model attributes**](https://github.com/adaptlearning/adapt_framework/wiki/Core-model-attributes): These are inherited by every Adapt component. [Read more](https://github.com/adaptlearning/adapt_framework/wiki/Core-model-attributes).

**_component** (string): This value must be: `assessmentResultsTotalAudio`. (One word with uppercase "R".)

**_classes** (string): CSS class name(s) to be applied to **Assessment Results Total Audio**’ containing `div`. The class(es) must be predefined in one of the Less files. Separate multiple classes with a space.

**_layout** (string): This defines the horizontal position of the component in the block. Values can be `full`, `left` or `right`.  

**instruction** (string): This optional text appears above the component. It is frequently used to
guide the learner’s interaction with the component.   

**_isVisibleBeforeCompletion** (boolean): Determines whether this component will be visible as the learner enters the assessment article or if it will be displayed only after the learner completes all question components. Acceptable values are `true` or `false`. The default is `false`.

**_retry** (object): Contains values for **button** and **feedback**.

>**button** (string): Text that appears on the retry button.

>**feedback** (string): This text is displayed only when both **_allowRetry** is `true` and more attempts remain ([configured in adapt-contrib-assessment](https://github.com/adaptlearning/adapt-contrib-assessment#attributes)). It may make use of the following variables: `{{attemptsSpent}}`, `{{attempts}}`, `{{attemptsLeft}}`, `{{score}}`, `{{scoreAsPercent}}` and `{{maxScore}}`. These values are populated with data supplied by [adapt-contrib-assessment](https://github.com/adaptlearning/adapt-contrib-assessment#attributes). `{{{feedback}}}`, representing the feedback assigned to the appropriate band within this component, is also allowed.  

**_completionBody** (string): This text overwrites the standard **body** attribute upon completion of the assessment. It may make use of the following variables: `{{attemptsSpent}}`, `{{attempts}}`, `{{attemptsLeft}}`, `{{score}}`, `{{scoreAsPercent}}` and `{{maxScore}}`. The variable `{{{feedback}}}`, representing the feedback assigned to the appropriate band, is also allowed.  

**_bands** (object array): Multiple items may be created. Each item represents the feedback and opportunity to retry for the appropriate range of scores. **_bands** contains values for **_score**, **feedback**, **_allowRetry** and **_classes**.

>**_score** (number):  This numeric value represents the raw score or percentile (as determined by the configuration of [adapt-contrib-assessment](https://github.com/adaptlearning/adapt-contrib-assessment)) that indicates the low end or start of the range. The range continues to the next highest **_score** of another band.

>**feedback** (string): This text will be displayed to the learner when the learner's score falls within this band's range. It replaces the `{{{feedback}}}` variable when the variable is used within **_completionBody**.

>**_allowRetry** (boolean): Determines whether the learner will be allowed to reattempt the assessment. If the value is `false`, the learner will not be allowed to retry the assessment regardless of any remaining attempts.  

>**_classes** (string): Classes that will be applied to the containing article if the user's score falls into this band. Allows for custom styling based on the feedback band.  

<div float align=right><a href="#top">Back to Top</a></div>

<img src="https://github.com/adaptlearning/documentation/blob/master/04_wiki_assets/plug-ins/images/assessmentResults02.png" alt="sample assessment results component" align="right">

In the image to the right, numbers are paired with the text's source attributes as follows:  
1. _displayTitle  
2. _bands.feedback  
3. {{scoreAsPercent}}  
4. _retry.button  


For a guide on the difference between using two curly braces and three curly braces when working with the variables that are available in this component, see [the HTML escaping section of the the Handlebars website](http://handlebarsjs.com/#html-escaping)

## Limitations

No known limitations.  

----------------------------
**Version number:**  2.0.8  
**Framework versions:** 2.0  
**Author / maintainer:** DeltaNet, forked from [adapt-contrib-assessmentResultsTotal](https://github.com/adaptlearning/adapt-contrib-assessmentResultsTotal)    
**Accessibility support:** WAI AA   
**RTL support:** yes  
**Cross-platform coverage:** Chrome, Chrome for Android, Firefox (ESR + latest version), Edge 12, IE 11, IE10, IE9, IE8, IE Mobile 11, Safari iOS 9+10, Safari OS X 9+10, Opera
