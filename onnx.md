# ONNX 구조 정리

```
ModelProto
├── ir_version
├── opset_import
├── producer_name / producer_version / domain / model_version
├── graph (GraphProto) ← ★ 모델의 핵심 연산 그래프
│   ├── input (ValueInfoProto)
│   ├── output (ValueInfoProto)
│   ├── initializer (TensorProto)
│   ├── sparse_initializer (SparseTensorProto)
│   ├── node (NodeProto) ← ★ 계산 노드 (Op 들)
│   ├── value_info (ValueInfoProto)
│   ├── quantization_annotation (TensorAnnotation)
│   └── metadata_props
├── metadata_props
├── training_info (TrainingInfoProto)
├── functions (FunctionProto)
└── configuration (DeviceConfigurationProto)
```

1. google protobuf
  - onnx는 2017년에 시작된 프로젝트이고, SNC는 이러한 onnx의 구조를 기반으로 만들어진 데이터 타입이다.
  - 모델 format 종류
  https://chatgpt.com/c/680d98a6-ed94-800c-bc43-5becc9c6bcc1
  ① protobuf (Protocol Buffers)
  ② flatbuffers
  ③ safetensor

2.


99. 대화 내용
  - https://chatgpt.com/c/680d5a94-c0dc-800c-81eb-51496a243426
