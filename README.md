## verbecc

#### Verbes, complètement conjugués - conjugueur français

#### Verbs, completely conjugated - French conjugator

https://github.com/bretttolbert/verbecc

[![Python Package Index Status](https://img.shields.io/pypi/v/verbecc.svg)](https://pypi.python.org/pypi/verbecc) [![GitLab CI pipeline status](https://gitlab.com/bretttolbert/verbecc/badges/master/pipeline.svg)](https://gitlab.com/bretttolbert/verbecc/pipelines)

#### Features
* Over 7,000 verbs supported
* pip installable
* Unit tested
* Continuous Integration and Deployment with GitLab CI/CD
* Dependencies: lxml

#### Credits
Created with the help of [lxml](https://github.com/lxml/lxml), [pytest](https://docs.pytest.org) and [python](https://www.python.org/). Verb conjugation template XML files derived from [Verbiste](https://perso.b2b2c.ca/~sarrazip/dev/verbiste.html)


## verbecc-svc

#### verbecc-svc Microservice Python avec un API REST pour la conjugaison des verbes français

#### verbecc-svc Python microservice with REST API for conjugation of French verbs

https://github.com/bretttolbert/verbecc-svc

[![pipeline status](https://gitlab.com/bretttolbert/verb-conjugate-fr/badges/master/pipeline.svg)](https://gitlab.com/bretttolbert/verb-conjugate-fr/pipelines)

#### Live demo
http://verbe.cc/vcfr/conjugate/manger

#### Features
* Dockerized microservice
* Unit tested
* Continuous Integration and Deployment with GitLab CI/CD
* RESTful API with JSON responses
* Dependencies: verbecc

#### Credits
Created with the help of [verbecc](https://github.com/bretttolbert/verbecc), [FastAPI](https://github.com/tiangolo/fastapi), [uvicorn](https://github.com/encode/uvicorn), [starlette](https://github.com/encode/starlette), [docker](https://docker.com), [docker-compose](https://docs.docker.com/compose/), [pytest](https://docs.pytest.org) and [python](https://www.python.org/).


## verbecc-web

#### Une interface web pour verbecc-svc

#### Web front-end for verbecc-svc

https://github.com/bretttolbert/verbecc-web

#### Live demo
http://verbe.cc

#### Features
* Dockerized
* Search suggestions
* Implemented entirely in Javascript (JQuery) - conjugations are generated without reloading the page
* Dependencies: verbecc-svc

#### Credits
Created with the help of [verbecc-svc](https://github.com/bretttolbert/verbecc-svc), and [JQuery](https://jquery.com/)


```
+------------------------------------------------------+                                                                               
|               verbecc-web                            |                                                                               
|               web application                        |                                                                               
|               docker-compose                         |                                                                               
|                      |                               |                                                                               
|                  REST API                            |                                                                               
|                      |                               |                                                                               
|      +----------------------------------------+      |                                                                               
|      |                                        |      |                                                                               
|      |       verbecc-svc                      |      |                                                                               
|      |       Dockerized microservice          |      |                                                                               
|      |                                        |      |                                                                               
|      |        +----------------------+        |      |                                                                               
|      |        |   verbecc            |        |      |                                                                               
|      |        |   Python library     |        |      |                                                                               
|      |        +----------------------+        |      |                                                                               
|      +----------------------------------------+      |                                                                               
+------------------------------------------------------+                                                                               
```   


Mode du verbe|"mood" API key
--- | ---
Infinitif | infinitive
Indicatif | indicative
Impératif | imperative
Conditionnel | conditional
Participe | participle

Temps du verbe|"tense" API key
--- | ---
Présent | present
Passé | past
Imparfait | imperfect
Future simple | future
Future antérieur | future-perfect
Passé antérieur | anterior-past
Passé composé | passé-composé
Plus-que-parfait | pluperfect


# verbecc-svc

#### Quick Start (Docker)
```
$ docker pull bretttolbert/verbecc-svc:latest
$ docker run -d -p 8000:8000 bretttolbert/verbecc-svc:latest
```

## Quick Start (Development)

```
$ make dev-build
$ make dev
```

## Usage Examples

* http://localhost:8000/conjugate/manger
```
{
  "value": {
    "verb": {
      "infinitive": "manger",
      "template": "man:ger",
      "translation_en": "eat",
      "stem": "man"
    },
    "moods": {
      "infinitive": {
        "infinitive-present": [
          "manger"
        ]
      },
      "indicative": {
        "present": [
          "je mange",
          "tu manges",
          "il mange",
          "nous mangeons",
          "vous mangez",
          "ils mangent"
        ],
        "imperfect": [
          "je mangeais",
          "tu mangeais",
          "il mangeait",
          "nous mangions",
          "vous mangiez",
          "ils mangeaient"
        ],
        "future": [
          "je mangerai",
          "tu mangeras",
          "il mangera",
          "nous mangerons",
          "vous mangerez",
          "ils mangeront"
        ],
        "simple-past": [
          "je mangeai",
          "tu mangeas",
          "il mangea",
          "nous mangeâmes",
          "vous mangeâtes",
          "ils mangèrent"
        ],
        "passé-composé": [
          "j'ai mangé",
          "tu as mangé",
          "il a mangé",
          "nous avons mangé",
          "vous avez mangé",
          "ils ont mangé"
        ],
        "pluperfect": [
          "j'avais mangé",
          "tu avais mangé",
          "il avait mangé",
          "nous avions mangé",
          "vous aviez mangé",
          "ils avaient mangé"
        ],
        "future-perfect": [
          "j'aurai mangé",
          "tu auras mangé",
          "il aura mangé",
          "nous aurons mangé",
          "vous aurez mangé",
          "ils auront mangé"
        ],
        "anterior-past": [
          "j'eus mangé",
          "tu eus mangé",
          "il eut mangé",
          "nous eûmes mangé",
          "vous eûtes mangé",
          "ils eurent mangé"
        ]
      },
      "conditional": {
        "present": [
          "je mangerais",
          "tu mangerais",
          "il mangerait",
          "nous mangerions",
          "vous mangeriez",
          "ils mangeraient"
        ],
        "past": [
          "j'aurais mangé",
          "tu aurais mangé",
          "il aurait mangé",
          "nous aurions mangé",
          "vous auriez mangé",
          "ils auraient mangé"
        ]
      },
      "subjunctive": {
        "present": [
          "que je mange",
          "que tu manges",
          "qu'il mange",
          "que nous mangions",
          "que vous mangiez",
          "qu'ils mangent"
        ],
        "imperfect": [
          "que je mangeasse",
          "que tu mangeasses",
          "qu'il mangeât",
          "que nous mangeassions",
          "que vous mangeassiez",
          "qu'ils mangeassent"
        ],
        "past": [
          "que j'aie mangé",
          "que tu aies mangé",
          "qu'il ait mangé",
          "que nous ayons mangé",
          "que vous ayez mangé",
          "qu'ils aient mangé"
        ],
        "pluperfect": [
          "que j'eusse mangé",
          "que tu eusses mangé",
          "qu'il eût mangé",
          "que nous eussions mangé",
          "que vous eussiez mangé",
          "qu'ils eussent mangé"
        ]
      },
      "imperative": {
        "imperative-present": [
          "mange",
          "mangeons",
          "mangez"
        ],
        "imperative-past": [
          "aie mangé",
          "ayons mangé",
          "ayez mangé"
        ]
      },
      "participle": {
        "present-participle": [
          "mangeant"
        ],
        "past-participle": [
          "mangé",
          "mangés",
          "mangée",
          "mangées"
        ]
      }
    }
  }
}
```

* http://localhost:8000/conjugate/se lever
```
{
  "value": {
    "verb": {
      "infinitive": "lever",
      "template": "l:ever",
      "translation_en": "lift",
      "stem": "l"
    },
    "moods": {
      "infinitive": {
        "infinitive-present": [
          "se lever"
        ]
      },
      "indicative": {
        "present": [
          "je me lève",
          "tu te lèves",
          "il se lève",
          "nous nous levons",
          "vous vous levez",
          "ils se lèvent"
        ],
        "imperfect": [
          "je me levais",
          "tu te levais",
          "il se levait",
          "nous nous levions",
          "vous vous leviez",
          "ils se levaient"
        ],
        "future": [
          "je me lèverai",
          "tu te lèveras",
          "il se lèvera",
          "nous nous lèverons",
          "vous vous lèverez",
          "ils se lèveront"
        ],
        "simple-past": [
          "je me levai",
          "tu te levas",
          "il se leva",
          "nous nous levâmes",
          "vous vous levâtes",
          "ils se levèrent"
        ],
        "passé-composé": [
          "je me suis levé",
          "tu t'es levé",
          "il s'est levé",
          "nous nous sommes levés",
          "vous vous êtes levés",
          "ils se sont levés"
        ],
        "pluperfect": [
          "je m'étais levé",
          "tu t'étais levé",
          "il s'était levé",
          "nous nous étions levés",
          "vous vous étiez levés",
          "ils s'étaient levés"
        ],
        "future-perfect": [
          "je me serai levé",
          "tu te seras levé",
          "il se sera levé",
          "nous nous serons levés",
          "vous vous serez levés",
          "ils se seront levés"
        ],
        "anterior-past": [
          "je me fus levé",
          "tu te fus levé",
          "il se fut levé",
          "nous nous fûmes levés",
          "vous vous fûtes levés",
          "ils se furent levés"
        ]
      },
      "conditional": {
        "present": [
          "je me lèverais",
          "tu te lèverais",
          "il se lèverait",
          "nous nous lèverions",
          "vous vous lèveriez",
          "ils se lèveraient"
        ],
        "past": [
          "je me serais levé",
          "tu te serais levé",
          "il se serait levé",
          "nous nous serions levés",
          "vous vous seriez levés",
          "ils se seraient levés"
        ]
      },
      "subjunctive": {
        "present": [
          "que je me lève",
          "que tu te lèves",
          "qu'il se lève",
          "que nous nous levions",
          "que vous vous leviez",
          "qu'ils se lèvent"
        ],
        "imperfect": [
          "que je me levasse",
          "que tu te levasses",
          "qu'il se levât",
          "que nous nous levassions",
          "que vous vous levassiez",
          "qu'ils se levassent"
        ],
        "past": [
          "que je me sois levé",
          "que tu te sois levé",
          "qu'il se soit levé",
          "que nous nous soyons levés",
          "que vous vous soyez levés",
          "qu'ils se soient levés"
        ],
        "pluperfect": [
          "que je me fusse levé",
          "que tu te fusses levé",
          "qu'il se fût levé",
          "que nous nous fussions levés",
          "que vous vous fussiez levés",
          "qu'ils se fussent levés"
        ]
      },
      "imperative": {
        "imperative-present": [
          "lève-toi",
          "levons-nous",
          "levez-vous"
        ],
        "imperative-past": []
      },
      "participle": {
        "present-participle": [
          "se levant"
        ],
        "past-participle": [
          "s'étant levé",
          "s'étant levés",
          "s'étant levée",
          "s'étant levées"
        ]
      }
    }
  }
}
```

* http://localhost:8000/find/infinitive/manger
```
{
  "value": {
    "infinitive": "manger",
    "template": "man:ger",
    "translation_en": "eat"
  }
}
```

* http://localhost:8000/search/infinitive/Se%20le
```
{
  "value": [
    "se lécher",
    "se léchouiller",
    "se légaliser",
    "se légender",
    "se légiférer",
    "se légitimer",
    "se léguer",
    "se lénifier",
    "se léser",
    "se lésiner"
  ]
}
```

* http://localhost:8000/conjugate/mood/indicative/manger
```
{
  "value": {
    "present": [
      "je mange",
      "tu manges",
      "il mange",
      "nous mangeons",
      "vous mangez",
      "ils mangent"
    ],
    "imperfect": [
      "je mangeais",
      "tu mangeais",
      "il mangeait",
      "nous mangions",
      "vous mangiez",
      "ils mangeaient"
    ],
    "future": [
      "je mangerai",
      "tu mangeras",
      "il mangera",
      "nous mangerons",
      "vous mangerez",
      "ils mangeront"
    ],
    "simple-past": [
      "je mangeai",
      "tu mangeas",
      "il mangea",
      "nous mangeâmes",
      "vous mangeâtes",
      "ils mangèrent"
    ],
    "passé-composé": [
      "j'ai mangé",
      "tu as mangé",
      "il a mangé",
      "nous avons mangé",
      "vous avez mangé",
      "ils ont mangé"
    ],
    "pluperfect": [
      "j'avais mangé",
      "tu avais mangé",
      "il avait mangé",
      "nous avions mangé",
      "vous aviez mangé",
      "ils avaient mangé"
    ],
    "future-perfect": [
      "j'aurai mangé",
      "tu auras mangé",
      "il aura mangé",
      "nous aurons mangé",
      "vous aurez mangé",
      "ils auront mangé"
    ],
    "anterior-past": [
      "j'eus mangé",
      "tu eus mangé",
      "il eut mangé",
      "nous eûmes mangé",
      "vous eûtes mangé",
      "ils eurent mangé"
    ]
  }
}
```

* http://localhost:8000/find/conjugation-template/man:ger

