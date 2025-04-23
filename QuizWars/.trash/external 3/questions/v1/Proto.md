# API Reference

# Table of Contents


- Services
    - [QuestionsAdminService](#questionsservicev1questionsadminservice)
  


- Messages
    - [CategoryFilter](#categoryfilter)
    - [CreateCategoryRequest](#createcategoryrequest)
    - [CreateCategoryResponse](#createcategoryresponse)
    - [CreateQuestionRequest](#createquestionrequest)
    - [CreatedAtFilter](#createdatfilter)
    - [DeleteQuestionOptionRequest](#deletequestionoptionrequest)
    - [DeleteQuestionRequest](#deletequestionrequest)
    - [DifficultyFilter](#difficultyfilter)
    - [GetFilteredQuestionsRequest](#getfilteredquestionsrequest)
    - [GetFilteredQuestionsResponse](#getfilteredquestionsresponse)
    - [LanguageFilter](#languagefilter)
    - [TypeFilter](#typefilter)
    - [UpdateCategoryRequest](#updatecategoryrequest)
    - [UpdateQuestionOptionRequest](#updatequestionoptionrequest)
    - [UpdateQuestionRequest](#updatequestionrequest)
  


- Enums
    - [Order](#order)
    - [Sort](#sort)
  



- Services
    - [QuestionsClientService](#questionsservicev1questionsclientservice)
  


- Messages
    - [GetCategoriesResponse](#getcategoriesresponse)
  




- Services
    - [QuestionsService](#questionsservicev1questionsservice)
  


- Messages
    - [GetQuestionBatchRequest](#getquestionbatchrequest)
    - [GetQuestionsRequest](#getquestionsrequest)
    - [QuestionsResponse](#questionsresponse)
  





- Messages
    - [Category](#category)
    - [Option](#option)
    - [Question](#question)
  


- Enums
    - [Difficulty](#difficulty)
    - [Source](#source)
    - [Type](#type)
  


- [Scalar Value Types](#scalar-value-types)



# QuestionsAdminService {#questionsservicev1questionsadminservice}


## GetFilteredQuestions

> **rpc** GetFilteredQuestions([GetFilteredQuestionsRequest](#getfilteredquestionsrequest))
    [GetFilteredQuestionsResponse](#getfilteredquestionsresponse)


## CreateCategory

> **rpc** CreateCategory([CreateCategoryRequest](#createcategoryrequest))
    [CreateCategoryResponse](#createcategoryresponse)


## CreateQuestion

> **rpc** CreateQuestion([CreateQuestionRequest](#createquestionrequest))
    [.google.protobuf.Empty](#googleprotobufempty)


## UpdateCategory

> **rpc** UpdateCategory([UpdateCategoryRequest](#updatecategoryrequest))
    [.google.protobuf.Empty](#googleprotobufempty)


## UpdateQuestion

> **rpc** UpdateQuestion([UpdateQuestionRequest](#updatequestionrequest))
    [.google.protobuf.Empty](#googleprotobufempty)


## UpdateQuestionOption

> **rpc** UpdateQuestionOption([UpdateQuestionOptionRequest](#updatequestionoptionrequest))
    [.google.protobuf.Empty](#googleprotobufempty)


## DeleteQuestion

> **rpc** DeleteQuestion([DeleteQuestionRequest](#deletequestionrequest))
    [.google.protobuf.Empty](#googleprotobufempty)


## DeleteQuestionOption

> **rpc** DeleteQuestionOption([DeleteQuestionOptionRequest](#deletequestionoptionrequest))
    [.google.protobuf.Empty](#googleprotobufempty)


 <!-- end methods -->
 <!-- end services -->

# Messages


## CategoryFilter {#categoryfilter}



| Field | Type | Description |
| ----- | ---- | ----------- |
| categories | [repeated int32](#int32) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreateCategoryRequest {#createcategoryrequest}



| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreateCategoryResponse {#createcategoryresponse}



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int32](#int32) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreateQuestionRequest {#createquestionrequest}



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


## CreatedAtFilter {#createdatfilter}



| Field | Type | Description |
| ----- | ---- | ----------- |
| from | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | none |
| to | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## DeleteQuestionOptionRequest {#deletequestionoptionrequest}



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## DeleteQuestionRequest {#deletequestionrequest}



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## DifficultyFilter {#difficultyfilter}



| Field | Type | Description |
| ----- | ---- | ----------- |
| difficulties | [repeated Difficulty](#difficulty) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetFilteredQuestionsRequest {#getfilteredquestionsrequest}



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


## GetFilteredQuestionsResponse {#getfilteredquestionsresponse}



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


## LanguageFilter {#languagefilter}



| Field | Type | Description |
| ----- | ---- | ----------- |
| languages | [repeated string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## TypeFilter {#typefilter}



| Field | Type | Description |
| ----- | ---- | ----------- |
| types | [repeated Type](#type) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateCategoryRequest {#updatecategoryrequest}



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int32](#int32) | none |
| name | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateQuestionOptionRequest {#updatequestionoptionrequest}



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _text.text | [optional string](#string) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _is_correct.is_correct | [optional bool](#bool) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateQuestionRequest {#updatequestionrequest}



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

# Enums


## Order {#order}


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




## Sort {#sort}


| Name | Number | Description |
| ---- | ------ | ----------- |
| SORT_UNSPECIFIED | 0 | none |
| SORT_ASC | 1 | none |
| SORT_DESC | 2 | none |


 <!-- end Enums -->


# QuestionsClientService {#questionsservicev1questionsclientservice}


## GetCategories

> **rpc** GetCategories([.google.protobuf.Empty](#googleprotobufempty))
    [GetCategoriesResponse](#getcategoriesresponse)


 <!-- end methods -->
 <!-- end services -->

# Messages


## GetCategoriesResponse {#getcategoriesresponse}



| Field | Type | Description |
| ----- | ---- | ----------- |
| categories | [repeated Category](#category) | none |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

# Enums
 <!-- end Enums -->


# QuestionsService {#questionsservicev1questionsservice}


## GetQuestions

> **rpc** GetQuestions([GetQuestionsRequest](#getquestionsrequest))
    [QuestionsResponse](#questionsresponse)


## GetQuestionBatch

> **rpc** GetQuestionBatch([GetQuestionBatchRequest](#getquestionbatchrequest))
    [QuestionsResponse](#questionsresponse)


 <!-- end methods -->
 <!-- end services -->

# Messages


## GetQuestionBatchRequest {#getquestionbatchrequest}



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


## GetQuestionsRequest {#getquestionsrequest}



| Field | Type | Description |
| ----- | ---- | ----------- |
| difficulty | [ Difficulty](#difficulty) | none |
| language | [ string](#string) | none |
| category_id | [ int32](#int32) | none |
| amount | [ int32](#int32) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## QuestionsResponse {#questionsresponse}



| Field | Type | Description |
| ----- | ---- | ----------- |
| questions | [repeated Question](#question) | none |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

# Enums
 <!-- end Enums -->


 <!-- end services -->

# Messages


## Category {#category}



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ int32](#int32) | none |
| name | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## Option {#option}



| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | none |
| text | [ string](#string) | none |
| is_correct | [ bool](#bool) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## Question {#question}



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

# Enums


## Difficulty {#difficulty}


| Name | Number | Description |
| ---- | ------ | ----------- |
| DIFFICULTY_UNSPECIFIED | 0 | none |
| DIFFICULTY_EASY | 1 | none |
| DIFFICULTY_MEDIUM | 2 | none |
| DIFFICULTY_HARD | 3 | none |
| DIFFICULTY_VERY_HARD | 4 | none |




## Source {#source}


| Name | Number | Description |
| ---- | ------ | ----------- |
| SOURCE_UNSPECIFIED | 0 | none |
| SOURCE_TEXT | 1 | none |
| SOURCE_IMAGE | 2 | none |
| SOURCE_AUDIO | 3 | none |
| SOURCE_ANIMATION | 4 | none |
| SOURCE_VIDEO | 5 | none |




## Type {#type}


| Name | Number | Description |
| ---- | ------ | ----------- |
| TYPE_UNSPECIFIED | 0 | none |
| TYPE_SINGLE | 1 | none |
| TYPE_MULTI | 2 | none |
| TYPE_BETTING | 3 | none |


 <!-- end Enums -->
 <!-- end Files -->

# Scalar Value Types

| .proto Type | Notes | C++ Type | Java Type | Python Type |
| ----------- | ----- | -------- | --------- | ----------- |
| <div><h4 id="double" /></div><a name="double" /> double |  | double | double | float |
| <div><h4 id="float" /></div><a name="float" /> float |  | float | float | float |
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
| <div><h4 id="bytes" /></div><a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str |
