# TensorFlowApplication

On API 31 and lower devices the instrumented test inside this project succeeds, but on API 32 devices it requires `NnApiDelegate.Options#setUseNnapiCpu(true)`.

Otherwise it fails with an exception:

```
    java.lang.IllegalArgumentException: Internal error: Failed to apply delegate: NN API returned error ANEURALNETWORKS_OP_FAILED at line 4483 while completing NNAPI compilation.
    
    Node number 7 (TfLiteNnapiDelegate) failed to prepare.
    Restored original execution plan after delegate application failure.
        at org.tensorflow.lite.NativeInterpreterWrapper.createInterpreter(Native Method)
        at org.tensorflow.lite.NativeInterpreterWrapper.init(NativeInterpreterWrapper.java:93)
        at org.tensorflow.lite.NativeInterpreterWrapper.<init>(NativeInterpreterWrapper.java:66)
        at org.tensorflow.lite.NativeInterpreterWrapperExperimental.<init>(NativeInterpreterWrapperExperimental.java:44)
        at org.tensorflow.lite.Interpreter.<init>(Interpreter.java:226)
```

This project was based off Android Studio's "New Project" wizard, and stripping out as much as possible
for clarity.
