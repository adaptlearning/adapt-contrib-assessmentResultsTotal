#adapt-contrib-asessmentResultsTotal

An Adapt core component used to display the total assessment results.

##Installation

First, be sure to install the [Adapt Command Line Interface](https://github.com/adaptlearning/adapt-cli), then from the command line run:-

        adapt install adapt-contrib-asessmentResultsTotal

This component can also be installed by adding the component to the adapt.json file before running `adapt install`:
 
        "adapt-contrib-asessmentResultsTotal": "*"

##Usage

It can only be used in conjunction with [adapt-contrib-assessment](https://github.com/adaptlearning/adapt-contrib-assessment). Feedback is worked out in this component and should match the scoreToPass variable from the course.


##Settings overview

For example JSON format, see [example.json](example.json). A description of the core settings can be found at: [Core model attributes](https://github.com/adaptlearning/adapt_framework/wiki/Core-model-attributes)

####components.json

```json
  {
    "_id":"c-135",
    "_parentId":"b-32",
    "_type":"component",
    "_component":"assessmentResultsTotal",
    "_classes":"",
    "_layout":"full",
    "title":"Total Results",
    "displayTitle":"Total Results",
    "body":"This component you're reading is a total results component.",
    "instruction":"",
    "_pageLevelProgress": {
      "_isEnabled": true
    },
    "_completionBody": "This component you're reading is a total results component.<br>You have finished the assessments.<br>You scored {{{scoreAsPercent}}}%. {{{feedback}}}",
    "_bands": [
      {
        "_score": 0,
        "feedback": "Your overall score was below 25%."
      },
      {
        "_score": 25,
        "feedback": "Your overall score was below 50%."
      },
      {
        "_score": 50,
        "feedback": "Good effort, but your overall score was under 75%."
      },
      {
        "_score": 75,
        "feedback": "Great work. You passed your assessments."
      }
    ]
  },
```

A description of the attributes is as follows:

| Attribute                 | Type         | Description|
| :-------------------------|:-------------|:-----|
| _completionBody           | string       | This is an string describing the component's body on assessment completion |
| _bands                    | object array | This is an array containing bands of feedback starting at _score |


The {{{attributes}}} available for string replacement are defined in the [assessment extension](https://github.com/adaptlearning/adapt-contrib-assessment) with the addition of the {{{feedback}}} attribute.

##Limitations
 
To be completed.

##Browser spec

This component has been tested to the standard Adapt browser specification.