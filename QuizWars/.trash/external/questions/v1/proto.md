# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [external/questions/v1/admin.proto](#external_questions_v1_admin-proto)
    - [QuestionsAdminService](#questionsservice-v1-QuestionsAdminService)
  
    - [CategoryFilter](#questionsservice-v1-CategoryFilter)
    - [CreateCategoryRequest](#questionsservice-v1-CreateCategoryRequest)
    - [CreateCategoryResponse](#questionsservice-v1-CreateCategoryResponse)
    - [CreateQuestionRequest](#questionsservice-v1-CreateQuestionRequest)
    - [CreatedAtFilter](#questionsservice-v1-CreatedAtFilter)
    - [DeleteQuestionOptionRequest](#questionsservice-v1-DeleteQuestionOptionRequest)
    - [DeleteQuestionRequest](#questionsservice-v1-DeleteQuestionRequest)
    - [DifficultyFilter](#questionsservice-v1-DifficultyFilter)
    - [GetFilteredQuestionsRequest](#questionsservice-v1-GetFilteredQuestionsRequest)
    - [GetFilteredQuestionsResponse](#questionsservice-v1-GetFilteredQuestionsResponse)
    - [LanguageFilter](#questionsservice-v1-LanguageFilter)
    - [TypeFilter](#questionsservice-v1-TypeFilter)
    - [UpdateCategoryRequest](#questionsservice-v1-UpdateCategoryRequest)
    - [UpdateQuestionOptionRequest](#questionsservice-v1-UpdateQuestionOptionRequest)
    - [UpdateQuestionRequest](#questionsservice-v1-UpdateQuestionRequest)
  
    - [Order](#questionsservice-v1-Order)
    - [Sort](#questionsservice-v1-Sort)
  
- [external/questions/v1/client.proto](#external_questions_v1_client-proto)
    - [QuestionsClientService](#questionsservice-v1-QuestionsClientService)
  
    - [GetCategoriesResponse](#questionsservice-v1-GetCategoriesResponse)
  
- [external/questions/v1/questions.proto](#external_questions_v1_questions-proto)
    - [QuestionsService](#questionsservice-v1-QuestionsService)
  
    - [GetQuestionBatchRequest](#questionsservice-v1-GetQuestionBatchRequest)
    - [GetQuestionsRequest](#questionsservice-v1-GetQuestionsRequest)
    - [QuestionsResponse](#questionsservice-v1-QuestionsResponse)
  
- [external/questions/v1/shared.proto](#external_questions_v1_shared-proto)
    - [Category](#questionsservice-v1-Category)
    - [Option](#questionsservice-v1-Option)
    - [Question](#questionsservice-v1-Question)
  
    - [Difficulty](#questionsservice-v1-Difficulty)
    - [Source](#questionsservice-v1-Source)
    - [Type](#questionsservice-v1-Type)
  
- [Scalar Value Types](#scalar-value-types)



<a name="external_questions_v1_admin-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/questions/v1/admin.proto



<a name="questionsservice-v1-CategoryFilter"></a>

### CategoryFilter



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| categories | [int32](#int32) | repeated |  |






<a name="questionsservice-v1-CreateCategoryRequest"></a>

### CreateCategoryRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) |  |  |






<a name="questionsservice-v1-CreateCategoryResponse"></a>

### CreateCategoryResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [int32](#int32) |  |  |






<a name="questionsservice-v1-CreateQuestionRequest"></a>

### CreateQuestionRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [Type](#questionsservice-v1-Type) |  |  |
| difficulty | [Difficulty](#questionsservice-v1-Difficulty) |  |  |
| category_id | [int32](#int32) |  |  |
| text | [string](#string) |  |  |
| options | [Option](#questionsservice-v1-Option) | repeated |  |
| language | [string](#string) |  |  |
| media_url | [string](#string) | optional |  |






<a name="questionsservice-v1-CreatedAtFilter"></a>

### CreatedAtFilter



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| from | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| to | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |






<a name="questionsservice-v1-DeleteQuestionOptionRequest"></a>

### DeleteQuestionOptionRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |






<a name="questionsservice-v1-DeleteQuestionRequest"></a>

### DeleteQuestionRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |






<a name="questionsservice-v1-DifficultyFilter"></a>

### DifficultyFilter



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| difficulties | [Difficulty](#questionsservice-v1-Difficulty) | repeated |  |






<a name="questionsservice-v1-GetFilteredQuestionsRequest"></a>

### GetFilteredQuestionsRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint64](#uint64) |  |  |
| size | [uint64](#uint64) |  |  |
| order | [Order](#questionsservice-v1-Order) | optional |  |
| sort | [Sort](#questionsservice-v1-Sort) | optional |  |
| type_filter | [TypeFilter](#questionsservice-v1-TypeFilter) | optional |  |
| difficulty_filter | [DifficultyFilter](#questionsservice-v1-DifficultyFilter) | optional |  |
| category_filter | [CategoryFilter](#questionsservice-v1-CategoryFilter) | optional |  |
| language_filter | [LanguageFilter](#questionsservice-v1-LanguageFilter) | optional |  |
| create_at_filter | [CreatedAtFilter](#questionsservice-v1-CreatedAtFilter) | optional |  |






<a name="questionsservice-v1-GetFilteredQuestionsResponse"></a>

### GetFilteredQuestionsResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| questions | [Question](#questionsservice-v1-Question) | repeated |  |
| page | [uint64](#uint64) |  |  |
| size | [uint64](#uint64) |  |  |
| order | [Order](#questionsservice-v1-Order) |  |  |
| sort | [Sort](#questionsservice-v1-Sort) |  |  |
| amount | [int64](#int64) |  |  |






<a name="questionsservice-v1-LanguageFilter"></a>

### LanguageFilter



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| languages | [string](#string) | repeated |  |






<a name="questionsservice-v1-TypeFilter"></a>

### TypeFilter



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| types | [Type](#questionsservice-v1-Type) | repeated |  |






<a name="questionsservice-v1-UpdateCategoryRequest"></a>

### UpdateCategoryRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [int32](#int32) |  |  |
| name | [string](#string) |  |  |






<a name="questionsservice-v1-UpdateQuestionOptionRequest"></a>

### UpdateQuestionOptionRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |
| text | [string](#string) | optional |  |
| is_correct | [bool](#bool) | optional |  |






<a name="questionsservice-v1-UpdateQuestionRequest"></a>

### UpdateQuestionRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |
| type | [Type](#questionsservice-v1-Type) | optional |  |
| difficulty | [Difficulty](#questionsservice-v1-Difficulty) | optional |  |
| category_id | [int32](#int32) | optional |  |
| text | [string](#string) | optional |  |
| language | [string](#string) | optional |  |





 <!-- end messages -->


<a name="questionsservice-v1-Order"></a>

### Order


| Name | Number | Description |
| ---- | ------ | ----------- |
| ORDER_UNSPECIFIED | 0 |  |
| ORDER_ID | 1 |  |
| ORDER_TEXT | 2 |  |
| ORDER_TYPE | 3 |  |
| ORDER_DIFFICULTY | 4 |  |
| ORDER_CATEGORY | 5 |  |
| ORDER_LANGUAGE | 6 |  |
| ORDER_CREATED_AT | 7 |  |



<a name="questionsservice-v1-Sort"></a>

### Sort


| Name | Number | Description |
| ---- | ------ | ----------- |
| SORT_UNSPECIFIED | 0 |  |
| SORT_ASC | 1 |  |
| SORT_DESC | 2 |  |


 <!-- end enums -->

 <!-- end HasExtensions -->


<a name="questionsservice-v1-QuestionsAdminService"></a>

### QuestionsAdminService


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetFilteredQuestions | [GetFilteredQuestionsRequest](#questionsservice-v1-GetFilteredQuestionsRequest) | [GetFilteredQuestionsResponse](#questionsservice-v1-GetFilteredQuestionsResponse) |  |
| CreateCategory | [CreateCategoryRequest](#questionsservice-v1-CreateCategoryRequest) | [CreateCategoryResponse](#questionsservice-v1-CreateCategoryResponse) |  |
| CreateQuestion | [CreateQuestionRequest](#questionsservice-v1-CreateQuestionRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| UpdateCategory | [UpdateCategoryRequest](#questionsservice-v1-UpdateCategoryRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| UpdateQuestion | [UpdateQuestionRequest](#questionsservice-v1-UpdateQuestionRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| UpdateQuestionOption | [UpdateQuestionOptionRequest](#questionsservice-v1-UpdateQuestionOptionRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| DeleteQuestion | [DeleteQuestionRequest](#questionsservice-v1-DeleteQuestionRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |
| DeleteQuestionOption | [DeleteQuestionOptionRequest](#questionsservice-v1-DeleteQuestionOptionRequest) | [.google.protobuf.Empty](#google-protobuf-Empty) |  |

 <!-- end services -->



<a name="external_questions_v1_client-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/questions/v1/client.proto



<a name="questionsservice-v1-GetCategoriesResponse"></a>

### GetCategoriesResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| categories | [Category](#questionsservice-v1-Category) | repeated |  |





 <!-- end messages -->

 <!-- end enums -->

 <!-- end HasExtensions -->


<a name="questionsservice-v1-QuestionsClientService"></a>

### QuestionsClientService


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetCategories | [.google.protobuf.Empty](#google-protobuf-Empty) | [GetCategoriesResponse](#questionsservice-v1-GetCategoriesResponse) |  |

 <!-- end services -->



<a name="external_questions_v1_questions-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/questions/v1/questions.proto



<a name="questionsservice-v1-GetQuestionBatchRequest"></a>

### GetQuestionBatchRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| types | [Type](#questionsservice-v1-Type) | repeated |  |
| sources | [Source](#questionsservice-v1-Source) | repeated |  |
| difficulties | [Difficulty](#questionsservice-v1-Difficulty) | repeated |  |
| categories_ids | [int32](#int32) | repeated |  |
| language | [string](#string) |  |  |
| amount | [int32](#int32) |  |  |






<a name="questionsservice-v1-GetQuestionsRequest"></a>

### GetQuestionsRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| difficulty | [Difficulty](#questionsservice-v1-Difficulty) |  |  |
| language | [string](#string) |  |  |
| category_id | [int32](#int32) |  |  |
| amount | [int32](#int32) |  |  |






<a name="questionsservice-v1-QuestionsResponse"></a>

### QuestionsResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| questions | [Question](#questionsservice-v1-Question) | repeated |  |





 <!-- end messages -->

 <!-- end enums -->

 <!-- end HasExtensions -->


<a name="questionsservice-v1-QuestionsService"></a>

### QuestionsService


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetQuestions | [GetQuestionsRequest](#questionsservice-v1-GetQuestionsRequest) | [QuestionsResponse](#questionsservice-v1-QuestionsResponse) |  |
| GetQuestionBatch | [GetQuestionBatchRequest](#questionsservice-v1-GetQuestionBatchRequest) | [QuestionsResponse](#questionsservice-v1-QuestionsResponse) |  |

 <!-- end services -->



<a name="external_questions_v1_shared-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## external/questions/v1/shared.proto



<a name="questionsservice-v1-Category"></a>

### Category



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [int32](#int32) |  |  |
| name | [string](#string) |  |  |






<a name="questionsservice-v1-Option"></a>

### Option



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |
| text | [string](#string) |  |  |
| is_correct | [bool](#bool) |  |  |






<a name="questionsservice-v1-Question"></a>

### Question



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [string](#string) |  |  |
| type | [Type](#questionsservice-v1-Type) |  |  |
| source | [Source](#questionsservice-v1-Source) |  |  |
| difficulty | [Difficulty](#questionsservice-v1-Difficulty) |  |  |
| category | [Category](#questionsservice-v1-Category) |  |  |
| text | [string](#string) |  |  |
| options | [Option](#questionsservice-v1-Option) | repeated |  |
| language | [string](#string) |  |  |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |





 <!-- end messages -->


<a name="questionsservice-v1-Difficulty"></a>

### Difficulty


| Name | Number | Description |
| ---- | ------ | ----------- |
| DIFFICULTY_UNSPECIFIED | 0 |  |
| DIFFICULTY_EASY | 1 |  |
| DIFFICULTY_MEDIUM | 2 |  |
| DIFFICULTY_HARD | 3 |  |
| DIFFICULTY_VERY_HARD | 4 |  |



<a name="questionsservice-v1-Source"></a>

### Source


| Name | Number | Description |
| ---- | ------ | ----------- |
| SOURCE_UNSPECIFIED | 0 |  |
| SOURCE_TEXT | 1 |  |
| SOURCE_IMAGE | 2 |  |
| SOURCE_AUDIO | 3 |  |
| SOURCE_ANIMATION | 4 |  |
| SOURCE_VIDEO | 5 |  |



<a name="questionsservice-v1-Type"></a>

### Type


| Name | Number | Description |
| ---- | ------ | ----------- |
| TYPE_UNSPECIFIED | 0 |  |
| TYPE_SINGLE | 1 |  |
| TYPE_MULTI | 2 |  |
| TYPE_BETTING | 3 |  |


 <!-- end enums -->

 <!-- end HasExtensions -->

 <!-- end services -->



## Scalar Value Types

| .proto Type | Notes | C++ | Java | Python | Go | C# | PHP | Ruby |
| ----------- | ----- | --- | ---- | ------ | -- | -- | --- | ---- |
| <a name="double" /> double |  | double | double | float | float64 | double | float | Float |
| <a name="float" /> float |  | float | float | float | float32 | float | float | Float |
| <a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum or Fixnum (as required) |
| <a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum |
| <a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="bool" /> bool |  | bool | boolean | boolean | bool | bool | boolean | TrueClass/FalseClass |
| <a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode | string | string | string | String (UTF-8) |
| <a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str | []byte | ByteString | string | String (ASCII-8BIT) |
