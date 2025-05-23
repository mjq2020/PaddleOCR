---
comments: true
---

# OCR Model List（V3, updated on 2022.4.28）
>
> **Note**
>
> 1. Compared with model v2, the 3rd version of the detection model has an improvement in accuracy, and the 2.1 version of the recognition model has optimizations in accuracy and speed with CPU.
> 2. Compared with [models 1.1](https://github.com/PaddlePaddle/PaddleOCR/blob/develop/doc/doc_en/models_list_en.md), which are trained with static graph programming paradigm, models 2.0 or higher are the dynamic graph trained version and achieve close performance.
> 3. All models in this tutorial are from the PaddleOCR series, for more introduction to algorithms and models based on the public dataset, you can refer to [algorithm overview tutorial](../algorithm/overview.en.md).

The downloadable models provided by PaddleOCR include the `inference model`, `trained model`, `pre-trained model` and `nb model`. The differences between the models are as follows:

|model type|model format|description|
|--- | --- | --- |
|inference model|inference.pdmodel、inference.pdiparams|Used for inference based on Paddle inference engine，[detail](./infer_deploy/python_infer.en.md)|
|trained model, pre-trained model|\*.pdparams、\*.pdopt、\*.states |The checkpoints model saved in the training process, which stores the parameters of the model, is mostly used for model evaluation and continuous training.|
|nb model|\*.nb| Model optimized by Paddle-Lite, which is suitable for mobile-side deployment scenarios (Paddle-Lite is needed for nb model deployment). |

The relationship of the above models is as follows.

![](../imgs_en/model_prod_flow_en.png)

## 1. Text Detection Model

### 1. Chinese Detection Model

|model name|description|config|model size|download|
| --- | --- | --- | --- | --- |
| PP-OCRv4_mobile_det              | [New] Original lightweight model, supporting Chinese, English, multilingual text detection              | [PP-OCRv4_mobile_det.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/det/PP-OCRv4/PP-OCRv4_mobile_det.yml)         | 4.70M        | [inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/PP-OCRv4_mobile_det_infer.tar) / [trained model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_pretrained_model/PP-OCRv4_mobile_det_pretrained.pdparams)                |
| PP-OCRv4_server_det        | [New] Original high-precision model, supporting Chinese, English, multilingual text detection      | [PP-OCRv4_server_det.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/det/PP-OCRv4/PP-OCRv4_server_det.yml) | 110M         | [inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/PP-OCRv4_server_det_infer.tar) / [trained model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_pretrained_model/PP-OCRv4_server_det_pretrained.pdparams)  |
| PP-OCRv3_mobile_det        | Original lightweight model, supporting Chinese, English, multilingual text detection           | [PP-OCRv3_mobile_det.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/det/PP-OCRv3/PP-OCRv3_mobile_det.yml)         | 1.1M         | [inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/PP-OCRv3_mobile_det_infer.tar) / [trained model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_pretrained_model/PP-OCRv3_mobile_det_pretrained.pdparams) / [nb模型](https://paddleocr.bj.bcebos.com/PP-OCRv3/chinese/ch_PP-OCRv3_det_slim_infer.nb) |
| PP-OCRv3_server_det               |  Original high-precision model, supporting Chinese, English, multilingual text detection                           | [PP-OCRv3_server_det.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/det/PP-OCRv3/PP-OCRv3_server_det.yml)         | 3.80M        | [inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/PP-OCRv3_server_det_infer.tar) / [trained model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_pretrained_model/PP-OCRv3_server_det_pretrained.pdparams)  

### 1.2 English Detection Model

|model name|description|config|model size|download|
| --- | --- | --- | --- | --- |
|en_PP-OCRv3_det_slim | [New] Slim quantization with distillation lightweight detection model, supporting English | [PP-OCRv3_det_cml.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/det/PP-OCRv3/PP-OCRv3_mobile_det.yml) | 1.1M |[inference model](https://paddleocr.bj.bcebos.com/PP-OCRv3/english/en_PP-OCRv3_det_slim_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/english/en_PP-OCRv3_det_slim_distill_train.tar) / [nb model](https://paddleocr.bj.bcebos.com/PP-OCRv3/english/en_PP-OCRv3_det_slim_infer.nb) |
|en_PP-OCRv3_det | [New] Original lightweight detection model, supporting English |[PP-OCRv3_det_cml.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/det/PP-OCRv3/PP-OCRv3_mobile_det.yml)| 3.8M | [inference model](https://paddleocr.bj.bcebos.com/PP-OCRv3/english/en_PP-OCRv3_det_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/english/en_PP-OCRv3_det_distill_train.tar) |

* Note: English configuration file is the same as Chinese except for training data, here we only provide one configuration file.

### 1.3 Multilingual Detection Model

|model name|description|config|model size|download|
| --- | --- | --- | --- | --- |
| ml_PP-OCRv3_det_slim | [New] Slim quantization with distillation lightweight detection model, supporting English | [PP-OCRv3_det_cml.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/det/PP-OCRv3/PP-OCRv3_mobile_det.yml) | 1.1M | [inference model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/Multilingual_PP-OCRv3_det_slim_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/Multilingual_PP-OCRv3_det_slim_distill_train.tar) / [nb model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/Multilingual_PP-OCRv3_det_slim_infer.nb) |
| ml_PP-OCRv3_det |[New] Original lightweight detection model, supporting English | [PP-OCRv3_det_cml.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/det/PP-OCRv3/PP-OCRv3_mobile_det.yml)| 3.8M | [inference model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/Multilingual_PP-OCRv3_det_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/Multilingual_PP-OCRv3_det_distill_train.tar) |

* Note: English configuration file is the same as Chinese except for training data, here we only provide one configuration file.

## 2. Text Recognition Model

### 2.1 Chinese Recognition Model

|model name|description|config|model size|download|
| --- | --- | --- | --- | --- |
|PP-OCRv3_mobile_rec_slim | [New] Slim quantization with distillation lightweight model, supporting Chinese, English text recognition |[PP-OCRv3_mobile_rec_distillation.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/PP-OCRv3_mobile_rec_distillation.yml)| 4.9M |[inference model](https://paddleocr.bj.bcebos.com/PP-OCRv3/chinese/ch_PP-OCRv3_rec_slim_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/chinese/ch_PP-OCRv3_rec_slim_train.tar) / [nb model](https://paddleocr.bj.bcebos.com/PP-OCRv3/chinese/ch_PP-OCRv3_rec_slim_infer.nb) |
|PP-OCRv3_mobile_rec| [New] Original lightweight model, supporting Chinese, English, multilingual text recognition |[PP-OCRv3_mobile_rec_distillation.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/PP-OCRv3_mobile_rec_distillation.yml)| 12.4M |[inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/PP-OCRv3_mobile_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/chinese/ch_PP-OCRv3_rec_train.tar) |
|ch_PP-OCRv2_rec_slim| Slim quantization with distillation lightweight model, supporting Chinese, English text recognition|[ch_PP-OCRv2_rec.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/ch_PP-OCRv2/ch_PP-OCRv2_rec.yml)| 9.0M |[inference model](https://paddleocr.bj.bcebos.com/PP-OCRv2/chinese/ch_PP-OCRv2_rec_slim_quant_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv2/chinese/ch_PP-OCRv2_rec_slim_quant_train.tar) |
|ch_PP-OCRv2_rec| Original lightweight model, supporting Chinese, English, and multilingual text recognition |[ch_PP-OCRv2_rec_distillation.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/ch_PP-OCRv2/ch_PP-OCRv2_rec_distillation.yml)|8.5M|[inference model](https://paddleocr.bj.bcebos.com/PP-OCRv2/chinese/ch_PP-OCRv2_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv2/chinese/ch_PP-OCRv2_rec_train.tar) |
|ch_ppocr_mobile_slim_v2.0_rec|Slim pruned and quantized lightweight model, supporting Chinese, English and number recognition|[rec_chinese_lite_train_v2.0.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/ch_ppocr_v2.0/rec_chinese_lite_train_v2.0.yml)| 6.0M | [inference model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/ch/ch_ppocr_mobile_v2.0_rec_slim_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/ch/ch_ppocr_mobile_v2.0_rec_slim_train.tar) |
|ch_ppocr_mobile_v2.0_rec|Original lightweight model, supporting Chinese, English and number recognition|[rec_chinese_lite_train_v2.0.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/ch_ppocr_v2.0/rec_chinese_lite_train_v2.0.yml)|5.2M|[inference model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/ch/ch_ppocr_mobile_v2.0_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/ch/ch_ppocr_mobile_v2.0_rec_train.tar) / [pre-trained model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/ch/ch_ppocr_mobile_v2.0_rec_pre.tar) |
|ch_ppocr_server_v2.0_rec|General model, supporting Chinese, English and number recognition|[rec_chinese_common_train_v2.0.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/ch_ppocr_v2.0/rec_chinese_common_train_v2.0.yml)|94.8M|[inference model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/ch/ch_ppocr_server_v2.0_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/ch/ch_ppocr_server_v2.0_rec_train.tar) / [pre-trained model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/ch/ch_ppocr_server_v2.0_rec_pre.tar) |

**Note:** The `trained model` is fine-tuned on the `pre-trained model` with real data and synthesized vertical text data, which achieved better performance in the real scene. The `pre-trained model` is directly trained on the full amount of real data and synthesized data, which is more suitable for fine-tuning your dataset.

### 2.2 English Recognition Model

|model name|description|config|model size|download|
| --- | --- | --- | --- | --- |
|en_PP-OCRv3_mobile_rec_slim | [New] Slim quantization with distillation lightweight model, supporting English, English text recognition |[en_PP-OCRv3_mobile_rec.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/en_PP-OCRv3_mobile_rec.yml)| 3.2M |[inference model](https://paddleocr.bj.bcebos.com/PP-OCRv3/english/en_PP-OCRv3_rec_slim_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/english/en_PP-OCRv3_rec_slim_train.tar) / [nb model](https://paddleocr.bj.bcebos.com/PP-OCRv3/english/en_PP-OCRv3_rec_slim_infer.nb) |
|en_PP-OCRv3_mobile_rec| [New] Original lightweight model, supporting English, English, multilingual text recognition |[en_PP-OCRv3_mobile_rec.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/en_PP-OCRv3_mobile_rec.yml)| 9.6M |[inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/en_PP-OCRv3_mobile_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/english/en_PP-OCRv3_rec_train.tar) |
|en_number_mobile_slim_v2.0_rec|Slim pruned and quantized lightweight model, supporting English and number recognition|[rec_en_number_lite_train.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/multi_language/rec_en_number_lite_train.yml)| 2.7M | [inference model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/en/en_number_mobile_v2.0_rec_slim_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/en/en_number_mobile_v2.0_rec_slim_train.tar) |
|en_number_mobile_v2.0_rec|Original lightweight model, supporting English and number recognition|[rec_en_number_lite_train.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/multi_language/rec_en_number_lite_train.yml)|2.6M|[inference model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/multilingual/en_number_mobile_v2.0_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/multilingual/en_number_mobile_v2.0_rec_train.tar) |

**Note:** Dictionary file of all English recognition models is `ppocr/utils/en_dict.txt`.

### 2.3 Multilingual Recognition Model（Updating...）

|model name| dict file | description|config|model size|download|
| --- | --- | --- |--- | --- | --- |
| korean_PP-OCRv3_mobile_rec | ppocr/utils/dict/korean_dict.txt |Lightweight model for Korean recognition|[korean_PP-OCRv3_mobile_rec.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/multi_language/korean_PP-OCRv3_mobile_rec.yml)|11.0M|[inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/japan_PP-OCRv3_mobile_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/korean_PP-OCRv3_rec_train.tar) |
| japan_PP-OCRv3_mobile_rec | ppocr/utils/dict/japan_dict.txt |Lightweight model for Japanese recognition|[japan_PP-OCRv3_mobile_rec.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/multi_language/japan_PP-OCRv3_mobile_rec.yml)|11.0M|[inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/japan_PP-OCRv3_mobile_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/japan_PP-OCRv3_rec_train.tar) |
| chinese_cht_PP-OCRv3_mobile_rec | ppocr/utils/dict/chinese_cht_dict.txt | Lightweight model for chinese cht|[chinese_cht_PP-OCRv3_mobile_rec.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/multi_language/chinese_cht_PP-OCRv3_mobile_rec.yml)|12.0M|[inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/chinese_cht_PP-OCRv3_mobile_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/chinese_cht_PP-OCRv3_rec_train.tar) |
| te_PP-OCRv3_mobile_rec | ppocr/utils/dict/te_dict.txt | Lightweight model for Telugu recognition |[te_PP-OCRv3_mobile_rec.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/multi_language/te_PP-OCRv3_mobile_rec.yml)|9.6M|[inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/te_PP-OCRv3_mobile_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/te_PP-OCRv3_rec_train.tar) |
| ka_PP-OCRv3_mobile_rec | ppocr/utils/dict/ka_dict.txt | Lightweight model for Kannada recognition |[ka_PP-OCRv3_mobile_rec.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/multi_language/ka_PP-OCRv3_mobile_rec.yml)|9.9M|[inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/ka_PP-OCRv3_mobile_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/ka_PP-OCRv3_rec_train.tar) |
| ta_PP-OCRv3_mobile_rec | ppocr/utils/dict/ta_dict.txt |Lightweight model for Tamil recognition|[ta_PP-OCRv3_mobile_rec.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/multi_language/ta_PP-OCRv3_mobile_rec.yml)|9.6M|[inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/ta_PP-OCRv3_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/ta_PP-OCRv3_rec_train.tar) |
| latin_PP-OCRv3_mobile_rec |  ppocr/utils/dict/latin_dict.txt | Lightweight model for latin recognition |  [latin_PP-OCRv3_mobile_rec.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/multi_language/latin_PP-OCRv3_mobile_rec.yml) |9.7M|[inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/latin_PP-OCRv3_mobile_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/latin_PP-OCRv3_rec_train.tar) |
| arabic_PP-OCRv3_mobile_rec | ppocr/utils/dict/arabic_dict.txt | Lightweight model for arabic recognition  | [arabic_PP-OCRv3_mobile_rec.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/multi_language/arabic_PP-OCRv3_mobile_rec.yml) |9.6M|[inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/arabic_PP-OCRv3_mobile_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/arabic_PP-OCRv3_rec_train.tar) |
| cyrillic_PP-OCRv3_mobile_rec | ppocr/utils/dict/cyrillic_dict.txt | Lightweight model for cyrillic recognition  | [cyrillic_PP-OCRv3_mobile_rec.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/multi_language/cyrillic_PP-OCRv3_rec.yml) |9.6M|[inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/cyrillic_PP-OCRv3_mobile_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/cyrillic_PP-OCRv3_rec_train.tar) |
| devanagari_PP-OCRv3_mobile_rec | ppocr/utils/dict/devanagari_dict.txt | Lightweight model for devanagari recognition | [devanagari_PP-OCRv3_mobile_rec.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/rec/PP-OCRv3/multi_language/devanagari_PP-OCRv3_mobile_rec.yml) |9.9M|[inference model](https://paddle-model-ecology.bj.bcebos.com/paddlex/official_inference_model/paddle3.0.0/devanagari_PP-OCRv3_mobile_rec_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/devanagari_PP-OCRv3_rec_train.tar) |

For a complete list of languages ​​and tutorials, please refer to [Multi-language model](./blog/multi_languages.en.md)

## 3. Text Angle Classification Model

|model name|description|config|model size|download|
| --- | --- | --- | --- | --- |
|ch_ppocr_mobile_slim_v2.0_cls|Slim quantized model for text angle classification|[cls_mv3.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/cls/cls_mv3.yml)| 2.1M | [inference model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/ch/ch_ppocr_mobile_v2.0_cls_slim_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/ch/ch_ppocr_mobile_v2.0_cls_slim_train.tar) / [nb model](https://paddleocr.bj.bcebos.com/PP-OCRv2/lite/ch_ppocr_mobile_v2.0_cls_infer_opt.nb) |
|ch_ppocr_mobile_v2.0_cls|Original model for text angle classification|[cls_mv3.yml](https://github.com/PaddlePaddle/PaddleOCR/tree/main/configs/cls/cls_mv3.yml)|1.38M|[inference model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/ch/ch_ppocr_mobile_v2.0_cls_infer.tar) / [trained model](https://paddleocr.bj.bcebos.com/dygraph_v2.0/ch/ch_ppocr_mobile_v2.0_cls_train.tar) |

## 4. Paddle-Lite Model

Paddle Lite is an updated version of Paddle-Mobile, an open-open source deep learning framework designed to make it easy to perform inference on mobile, embedded, and IoT devices. It can further optimize the inference model and generate the `nb model` used for edge devices. It's suggested to optimize the quantization model using Paddle-Lite because the `INT8` format is used for the model storage and inference.

This chapter lists OCR nb models with PP-OCRv2 or earlier versions. You can access the latest nb models from the above tables.

|Version|Introduction|Model size|Detection model|Text Direction model|Recognition model|Paddle-Lite branch|
|---|---|---|---|---|---|---|
|PP-OCRv2|extra-lightweight chinese OCR optimized model|11.0M|[download link](https://paddleocr.bj.bcebos.com/PP-OCRv2/lite/ch_PP-OCRv2_det_infer_opt.nb)|[download link](https://paddleocr.bj.bcebos.com/PP-OCRv2/lite/ch_ppocr_mobile_v2.0_cls_infer_opt.nb)|[download link](https://paddleocr.bj.bcebos.com/PP-OCRv2/lite/ch_PP-OCRv2_rec_infer_opt.nb)|v2.10|
|PP-OCRv2(slim)|extra-lightweight chinese OCR optimized model|4.6M|[download link](https://paddleocr.bj.bcebos.com/PP-OCRv2/lite/ch_PP-OCRv2_det_slim_opt.nb)|[download link](https://paddleocr.bj.bcebos.com/PP-OCRv2/lite/ch_ppocr_mobile_v2.0_cls_slim_opt.nb)|[download link](https://paddleocr.bj.bcebos.com/PP-OCRv2/lite/ch_PP-OCRv2_rec_slim_opt.nb)|v2.10|
|PP-OCRv2|extra-lightweight chinese OCR optimized model|11.0M|[download link](https://paddleocr.bj.bcebos.com/PP-OCRv2/chinese/ch_PP-OCRv2_det_infer_opt.nb)|[download link](https://paddleocr.bj.bcebos.com/dygraph_v2.0/lite/ch_ppocr_mobile_v2.0_cls_opt.nb)|[download link](https://paddleocr.bj.bcebos.com/PP-OCRv2/chinese/ch_PP-OCRv2_rec_infer_opt.nb)|v2.9|
|PP-OCRv2(slim)|extra-lightweight chinese OCR optimized model|4.9M|[download link](https://paddleocr.bj.bcebos.com/PP-OCRv2/chinese/ch_PP-OCRv2_det_slim_opt.nb)|[download link](https://paddleocr.bj.bcebos.com/dygraph_v2.0/lite/ch_ppocr_mobile_v2.0_cls_slim_opt.nb)|[download link](https://paddleocr.bj.bcebos.com/PP-OCRv2/chinese/ch_PP-OCRv2_rec_slim_opt.nb)|v2.9|
|V2.0|ppocr_v2.0 extra-lightweight chinese OCR optimized model|7.8M|[download link](https://paddleocr.bj.bcebos.com/dygraph_v2.0/lite/ch_ppocr_mobile_v2.0_det_opt.nb)|[download link](https://paddleocr.bj.bcebos.com/dygraph_v2.0/lite/ch_ppocr_mobile_v2.0_cls_opt.nb)|[download link](https://paddleocr.bj.bcebos.com/dygraph_v2.0/lite/ch_ppocr_mobile_v2.0_rec_opt.nb)|v2.9|
|V2.0(slim)|ppocr_v2.0 extra-lightweight chinese OCR optimized model|3.3M|[download link](https://paddleocr.bj.bcebos.com/dygraph_v2.0/lite/ch_ppocr_mobile_v2.0_det_slim_opt.nb)|[download link](https://paddleocr.bj.bcebos.com/dygraph_v2.0/lite/ch_ppocr_mobile_v2.0_cls_slim_opt.nb)|[download link](https://paddleocr.bj.bcebos.com/dygraph_v2.0/lite/ch_ppocr_mobile_v2.0_rec_slim_opt.nb)|v2.9|
