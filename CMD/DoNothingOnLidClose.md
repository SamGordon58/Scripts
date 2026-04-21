```

::Do nothing when you close the lid
powercfg /setACvalueIndex scheme_current sub_buttons lidAction 0
powercfg /setDCvalueIndex scheme_current sub_buttons lidAction 0

::Re-activate current scheme to make settings take effect immediately
powercfg /setActive scheme_current
```