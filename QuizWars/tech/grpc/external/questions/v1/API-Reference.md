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


## GetFilteredQuestions



```proto
rpc GetFilteredQuestions(GetFilteredQuestionsRequest) returns (GetFilteredQuestionsResponse)
```
> Input: [[#GetFilteredQuestionsRequest]]
> Output: [[#GetFilteredQuestionsResponse]]

## CreateCategory



```proto
rpc CreateCategory(CreateCategoryRequest) returns (CreateCategoryResponse)
```
> Input: [[#CreateCategoryRequest]]
> Output: [[#CreateCategoryResponse]]

## CreateQuestion



```proto
rpc CreateQuestion(CreateQuestionRequest) returns (.google.protobuf.Empty)
```
> Input: [[#CreateQuestionRequest]]
> Output: [[#.google.protobuf.Empty]]

## UpdateCategory



```proto
rpc UpdateCategory(UpdateCategoryRequest) returns (.google.protobuf.Empty)
```
> Input: [[#UpdateCategoryRequest]]
> Output: [[#.google.protobuf.Empty]]

## UpdateQuestion



```proto
rpc UpdateQuestion(UpdateQuestionRequest) returns (.google.protobuf.Empty)
```
> Input: [[#UpdateQuestionRequest]]
> Output: [[#.google.protobuf.Empty]]

## UpdateQuestionOption



```proto
rpc UpdateQuestionOption(UpdateQuestionOptionRequest) returns (.google.protobuf.Empty)
```
> Input: [[#UpdateQuestionOptionRequest]]
> Output: [[#.google.protobuf.Empty]]

## DeleteQuestion



```proto
rpc DeleteQuestion(DeleteQuestionRequest) returns (.google.protobuf.Empty)
```
> Input: [[#DeleteQuestionRequest]]
> Output: [[#.google.protobuf.Empty]]

## DeleteQuestionOption



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
| categories | [repeated int32](#int32) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreateCategoryRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreateCategoryResponse



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int32](#int32) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreateQuestionRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| type | [ Type](#type) | none |
| difficulty | [ Difficulty](#difficulty) | none |
| category_id | [ int32](#int32) | none |
| text | [ string](#string) | none |
| options | [repeated Option](#option) | none |
| language | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _media_url.media_url | [optional string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreatedAtFilter



| Field | Type | Description |
| ----- | ---- | ----------- |
| from | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | none |
| to | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## DeleteQuestionOptionRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## DeleteQuestionRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## DifficultyFilter



| Field | Type | Description |
| ----- | ---- | ----------- |
| difficulties | [repeated Difficulty](#difficulty) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetFilteredQuestionsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| page | [ uint64](#uint64) | none |
| size | [ uint64](#uint64) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _order.order | [optional Order](#order) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _sort.sort | [optional Sort](#sort) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _type_filter.type_filter | [optional TypeFilter](#typefilter) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _difficulty_filter.difficulty_filter | [optional DifficultyFilter](#difficultyfilter) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _category_filter.category_filter | [optional CategoryFilter](#categoryfilter) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _language_filter.language_filter | [optional LanguageFilter](#languagefilter) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _create_at_filter.create_at_filter | [optional CreatedAtFilter](#createdatfilter) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetFilteredQuestionsResponse



| Field | Type | Description |
| ----- | ---- | ----------- |
| questions | [repeated Question](#question) | none |
| page | [ uint64](#uint64) | none |
| size | [ uint64](#uint64) | none |
| order | [ Order](#order) | none |
| sort | [ Sort](#sort) | none |
| amount | [ int64](#int64) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## LanguageFilter



| Field | Type | Description |
| ----- | ---- | ----------- |
| languages | [repeated string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## TypeFilter



| Field | Type | Description |
| ----- | ---- | ----------- |
| types | [repeated Type](#type) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateCategoryRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int32](#int32) | none |
| name | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateQuestionOptionRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _text.text | [optional string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _is_correct.is_correct | [optional bool](#bool) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateQuestionRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _type.type | [optional Type](#type) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _difficulty.difficulty | [optional Difficulty](#difficulty) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _category_id.category_id | [optional int32](#int32) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _text.text | [optional string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _language.language | [optional string](#string) | none |
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


## GetCategories



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


## GetQuestions



```proto
rpc GetQuestions(GetQuestionsRequest) returns (QuestionsResponse)
```
> Input: [[#GetQuestionsRequest]]
> Output: [[#QuestionsResponse]]

## GetQuestionBatch



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



| Field | Type | Description |
| ----- | ---- | ----------- |
| types | [repeated Type](#type) | none |
| sources | [repeated Source](#source) | none |
| difficulties | [repeated Difficulty](#difficulty) | none |
| categories_ids | [repeated int32](#int32) | none |
| language | [ string](#string) | none |
| amount | [ int32](#int32) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetQuestionsRequest



| Field | Type | Description |
| ----- | ---- | ----------- |
| difficulty | [ Difficulty](#difficulty) | none |
| language | [ string](#string) | none |
| category_id | [ int32](#int32) | none |
| amount | [ int32](#int32) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## QuestionsResponse



| Field | Type | Description |
| ----- | ---- | ----------- |
| questions | [repeated Question](#question) | none |
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



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int32](#int32) | none |
| name | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## Option



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
| text | [ string](#string) | none |
| is_correct | [ bool](#bool) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## Question



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
| type | [ Type](#type) | none |
| source | [ Source](#source) | none |
| difficulty | [ Difficulty](#difficulty) | none |
| category | [ Category](#category) | none |
| text | [ string](#string) | none |
| options | [repeated Option](#option) | none |
| language | [ string](#string) | none |
| created_at | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | none |
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
| TYPE_SINGLE | 1 | none |
| TYPE_MULTI | 2 | none |
| TYPE_BETTING | 3 | none |


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
