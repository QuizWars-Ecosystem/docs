# Table of Contents


> **external/questions/v1/admin.proto**

- Services
    - [[#QuestionsAdminService]]
  


- Messages
    - [[#CategoryFilter]]
    - [[#CreateCategoryRequest]]
    - [[#CreateCategoryResponse]]
    - [[#CreateQuestionRequest]]
    - [[#CreatedAtFilter]]
    - [[#DeleteQuestionOptionRequest]]
    - [[#DeleteQuestionRequest]]
    - [[#DifficultyFilter]]
    - [[#GetFilteredQuestionsRequest]]
    - [[#GetFilteredQuestionsResponse]]
    - [[#LanguageFilter]]
    - [[#TypeFilter]]
    - [[#UpdateCategoryRequest]]
    - [[#UpdateQuestionOptionRequest]]
    - [[#UpdateQuestionRequest]]
  


- Enums
    - [[#Order]]
    - [[#Sort]]
  

---

> **external/questions/v1/client.proto**

- Services
    - [[#QuestionsClientService]]
  


- Messages
    - [[#GetCategoriesResponse]]
  


---

> **external/questions/v1/questions.proto**

- Services
    - [[#QuestionsService]]
  


- Messages
    - [[#GetQuestionBatchRequest]]
    - [[#GetQuestionsRequest]]
    - [[#QuestionsResponse]]
  


---

> **external/questions/v1/shared.proto**


- Messages
    - [[#Category]]
    - [[#Option]]
    - [[#Question]]
  


- Enums
    - [[#Difficulty]]
    - [[#Source]]
    - [[#Type]]
  

---

> - [[#Scalar Value Types]]



# QuestionsAdminService
Questions Admin Service provides methods for admin's access and management

## GetFilteredQuestions

Method for getting paginated list of questions that can be requested with filters

```proto
rpc GetFilteredQuestions(GetFilteredQuestionsRequest) returns (GetFilteredQuestionsResponse)
```
> Input: [[#GetFilteredQuestionsRequest]]
> Output: [[#GetFilteredQuestionsResponse]]

## CreateCategory

Method for creating new category

```proto
rpc CreateCategory(CreateCategoryRequest) returns (CreateCategoryResponse)
```
> Input: [[#CreateCategoryRequest]]
> Output: [[#CreateCategoryResponse]]

## CreateQuestion

Method lets create a question with options

```proto
rpc CreateQuestion(CreateQuestionRequest) returns (.google.protobuf.Empty)
```
> Input: [[#CreateQuestionRequest]]
> Output: [[#.google.protobuf.Empty]]

## UpdateCategory

Method for updating existing category

```proto
rpc UpdateCategory(UpdateCategoryRequest) returns (.google.protobuf.Empty)
```
> Input: [[#UpdateCategoryRequest]]
> Output: [[#.google.protobuf.Empty]]

## UpdateQuestion

Method for updating question data by it's ID

```proto
rpc UpdateQuestion(UpdateQuestionRequest) returns (.google.protobuf.Empty)
```
> Input: [[#UpdateQuestionRequest]]
> Output: [[#.google.protobuf.Empty]]

## UpdateQuestionOption

Method for updating question's options

```proto
rpc UpdateQuestionOption(UpdateQuestionOptionRequest) returns (.google.protobuf.Empty)
```
> Input: [[#UpdateQuestionOptionRequest]]
> Output: [[#.google.protobuf.Empty]]

## DeleteQuestion

Method for deleting a question from database

```proto
rpc DeleteQuestion(DeleteQuestionRequest) returns (.google.protobuf.Empty)
```
> Input: [[#DeleteQuestionRequest]]
> Output: [[#.google.protobuf.Empty]]

## DeleteQuestionOption

Method for deleting a question's options from database

```proto
rpc DeleteQuestionOption(DeleteQuestionOptionRequest) returns (.google.protobuf.Empty)
```
> Input: [[#DeleteQuestionOptionRequest]]
> Output: [[#.google.protobuf.Empty]]

 <!-- end methods -->
 <!-- end services -->

---

# Messages


## CategoryFilter



| Field | Type | Description |
| ----- | ---- | ----------- |
| categories | [repeated int32](#int32) | List of desired questions categories |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreateCategoryRequest
Represents a request argument for creating new category


| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | Field is a name for new category |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreateCategoryResponse
Represents a response result of a request for creating category


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int32](#int32) | ID is ID of created category |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreateQuestionRequest
Represents a request argument for creating new questions with options


| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ Type](#type) | Question type |
| difficulty | [ Difficulty](#difficulty) | Difficulty of the question |
| category_id | [ int32](#int32) | Question's category ID |
| text | [ string](#string) | Text of the question |
| options | [repeated Option](#option) | Possible answers for the question |
| language | [ string](#string) | Language of the question |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _media_url.media_url | [optional string](#string) | Media URL if it has |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreatedAtFilter



| Field | Type | Description |
| ----- | ---- | ----------- |
| from | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | Start interval date for desired question |
| to | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | End interval date for desired question |
 <!-- end Fields -->
 <!-- end HasFields -->


## DeleteQuestionOptionRequest
Represent argument for deleting question's option request


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## DeleteQuestionRequest
Represent argument for deleting question request


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## DifficultyFilter



| Field | Type | Description |
| ----- | ---- | ----------- |
| difficulties | [repeated Difficulty](#difficulty) | List of desired questions difficulties |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetFilteredQuestionsRequest
Represents a componential argument of request for getting paginated questions with filters


| Field | Type | Description |
| ----- | ---- | ----------- |
| page | [ uint64](#uint64) | Page of the requested content, by default must me 1 |
| size | [ uint64](#uint64) | Amount of requesting questions |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _order.order | [optional Order](#order) | What order should be |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _sort.sort | [optional Sort](#sort) | Sort of the resulted questions |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _type_filter.type_filter | [optional TypeFilter](#typefilter) | What type of question should be |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _difficulty_filter.difficulty_filter | [optional DifficultyFilter](#difficultyfilter) | Desired difficulty of questions |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _category_filter.category_filter | [optional CategoryFilter](#categoryfilter) | Desired category |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _language_filter.language_filter | [optional LanguageFilter](#languagefilter) | What language of questions |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _create_at_filter.create_at_filter | [optional CreatedAtFilter](#createdatfilter) | When questions were created |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetFilteredQuestionsResponse
Represents a response of requested, filtered and paginated questions


| Field | Type | Description |
| ----- | ---- | ----------- |
| questions | [repeated Question](#question) | List of resulted questions |
| page | [ uint64](#uint64) | Current requested page |
| size | [ uint64](#uint64) | Amount of current |
| order | [ Order](#order) | Order of resulted questions list |
| sort | [ Sort](#sort) | Sort of resulted questions list |
| amount | [ int64](#int64) | Total amount of possible to request with the same request filter questions |
 <!-- end Fields -->
 <!-- end HasFields -->


## LanguageFilter



| Field | Type | Description |
| ----- | ---- | ----------- |
| languages | [repeated string](#string) | List of desired questions languages |
 <!-- end Fields -->
 <!-- end HasFields -->


## TypeFilter



| Field | Type | Description |
| ----- | ---- | ----------- |
| types | [repeated Type](#type) | List of desired questions types |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateCategoryRequest
Represents a argument of update category request


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int32](#int32) | none |
| name | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateQuestionOptionRequest
Represents a request argument for update question's option


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | ID of the option |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _text.text | [optional string](#string) | New text for option |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _is_correct.is_correct | [optional bool](#bool) | Is it right option or not |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateQuestionRequest
Represents a request argument for update question data, allows edit types, difficulty, category, text and language


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | ID of the question |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _type.type | [optional Type](#type) | New type |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _difficulty.difficulty | [optional Difficulty](#difficulty) | New difficulty |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _category_id.category_id | [optional int32](#int32) | New category of the question |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _text.text | [optional string](#string) | New text of the question |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _language.language | [optional string](#string) | New language for the language |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

---



# Enums


## Order


| Name | Number | Description |
| ---- | ------ | ----------- |
| ORDER_UNSPECIFIED | 0 | none |
| ORDER_ID | 1 | none |
| ORDER_TEXT | 2 | none |
| ORDER_TYPE | 3 | none |
| ORDER_DIFFICULTY | 4 | none |
| ORDER_CATEGORY | 5 | none |
| ORDER_LANGUAGE | 6 | none |
| ORDER_CREATED_AT | 7 | none |




## Sort


| Name | Number | Description |
| ---- | ------ | ----------- |
| SORT_UNSPECIFIED | 0 | none |
| SORT_ASC | 1 | none |
| SORT_DESC | 2 | none |


 <!-- end Enums -->
 <!-- end Files -->
---


# QuestionsClientService
Questions Client Service provides methods for clients

## GetCategories

Method allows get all existing categories

```proto
rpc GetCategories(.google.protobuf.Empty) returns (GetCategoriesResponse)
```
> Input: [[#.google.protobuf.Empty]]
> Output: [[#GetCategoriesResponse]]

 <!-- end methods -->
 <!-- end services -->

---

# Messages


## GetCategoriesResponse
Represents message with all existing categories is server


| Field | Type | Description |
| ----- | ---- | ----------- |
| categories | [repeated Category](#category) | none |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

---

 <!-- end Files -->
---


# QuestionsService
Questions service is a service for getting desired questions

## GetQuestions

Method for getting questions with light filter

```proto
rpc GetQuestions(GetQuestionsRequest) returns (QuestionsResponse)
```
> Input: [[#GetQuestionsRequest]]
> Output: [[#QuestionsResponse]]

## GetQuestionBatch

Method for getting batch of questions with heavy filter

```proto
rpc GetQuestionBatch(GetQuestionBatchRequest) returns (QuestionsResponse)
```
> Input: [[#GetQuestionBatchRequest]]
> Output: [[#QuestionsResponse]]

 <!-- end methods -->
 <!-- end services -->

---

# Messages


## GetQuestionBatchRequest
Represents a heavy filtered request for getting questions


| Field | Type | Description |
| ----- | ---- | ----------- |
| types | [repeated Type](#type) | List of desired question's types |
| sources | [repeated Source](#source) | List of desired questions' sources |
| difficulties | [repeated Difficulty](#difficulty) | List of desired question's difficulties |
| categories_ids | [repeated int32](#int32) | List of desired question's categories ids |
| language | [ string](#string) | Language of requesting question |
| amount | [ int32](#int32) | Amount of desired questions |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetQuestionsRequest
Represents a light filter for getting desired questions


| Field | Type | Description |
| ----- | ---- | ----------- |
| difficulty | [ Difficulty](#difficulty) | Desired difficulty |
| language | [ string](#string) | Desired question language |
| category_id | [ int32](#int32) | Desired question category id |
| amount | [ int32](#int32) | Amount of desired questions |
 <!-- end Fields -->
 <!-- end HasFields -->


## QuestionsResponse
Represents of requested, filtered questions list


| Field | Type | Description |
| ----- | ---- | ----------- |
| questions | [repeated Question](#question) | List of resulted questions |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

---

 <!-- end Files -->
---


 <!-- end services -->

---

# Messages


## Category
Message represents a category pf question


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int32](#int32) | ID is integer type |
| name | [ string](#string) | Name of category |
 <!-- end Fields -->
 <!-- end HasFields -->


## Option
Message represents a question's option


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | ID of option is UUID v4 |
| text | [ string](#string) | Text of question option |
| is_correct | [ bool](#bool) | Filed that shows is it correct answer or not |
 <!-- end Fields -->
 <!-- end HasFields -->


## Question
Message represents a question


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | ID of question is UUID v4 |
| type | [ Type](#type) | Type of question is a enum value |
| source | [ Source](#source) | Source of question is a enum value |
| difficulty | [ Difficulty](#difficulty) | Difficulty is a enum value |
| category | [ Category](#category) | Category is a pair of id of category and it's name |
| text | [ string](#string) | Text of a question |
| options | [repeated Option](#option) | List of question options |
| language | [ string](#string) | Language of a question |
| created_at | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | Date when a questing was added |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

---



# Enums


## Difficulty


| Name | Number | Description |
| ---- | ------ | ----------- |
| DIFFICULTY_UNSPECIFIED | 0 | none |
| DIFFICULTY_EASY | 1 | none |
| DIFFICULTY_MEDIUM | 2 | none |
| DIFFICULTY_HARD | 3 | none |
| DIFFICULTY_VERY_HARD | 4 | none |




## Source


| Name | Number | Description |
| ---- | ------ | ----------- |
| SOURCE_UNSPECIFIED | 0 | none |
| SOURCE_TEXT | 1 | none |
| SOURCE_IMAGE | 2 | none |
| SOURCE_AUDIO | 3 | none |
| SOURCE_ANIMATION | 4 | none |
| SOURCE_VIDEO | 5 | none |




## Type


| Name | Number | Description |
| ---- | ------ | ----------- |
| TYPE_UNSPECIFIED | 0 | none |
| TYPE_SINGLE | 1 | Question has definitely only one correct option |
| TYPE_MULTI | 2 | Question has one or more correct option |
| TYPE_BETTING | 3 | Question has ability make a bid on question answer |


 <!-- end Enums -->
 <!-- end Files -->
---


# Scalar Value Types

| .proto Type | Notes | Go Type | Java Type | Python Type |
| ----------- | ----- | -------- | --------- | ----------- |
| <div><h4 id="double" /></div><a name="double" /> double |  | float64 | double | float |
| <div><h4 id="float" /></div><a name="float" /> float |  | float32 | float | float |
| <div><h4 id="int32" /></div><a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int |
| <div><h4 id="int64" /></div><a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long |
| <div><h4 id="uint32" /></div><a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long |
| <div><h4 id="uint64" /></div><a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long |
| <div><h4 id="sint32" /></div><a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int |
| <div><h4 id="sint64" /></div><a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long |
| <div><h4 id="fixed32" /></div><a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int |
| <div><h4 id="fixed64" /></div><a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long |
| <div><h4 id="sfixed32" /></div><a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int |
| <div><h4 id="sfixed64" /></div><a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long |
| <div><h4 id="bool" /></div><a name="bool" /> bool |  | bool | boolean | boolean |
| <div><h4 id="string" /></div><a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode |
| <div><h4 id="bytes" /></div><a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | []byte | ByteString | str |
