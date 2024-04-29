## Mac specific work arounds for the notebooks

#### Adam Optimizer
tensorflow-metal package seems to have some problem with adam optimizer's implementation (something is missing).
Which might result in the below error:
> INVALID_ARGUMENT: Graph does not contain terminal node Adam/AssignAddVariableOp

Instead of using default Adam, use the Adam optimizer from legacy sub-package
`tf.keras.optimizers.legacy.Adam()`

*Example:*
```model.compile(optimizer=tf.keras.optimizers.legacy.Adam(learning_rate=1e-3), loss=loss_fn, metrics=["accuracy"])```


