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
