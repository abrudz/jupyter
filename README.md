# Dyalog In-Session Jupyter

*Run Jupyter Notebook document inside Dyalog APL session, optionally interactively.*

Requires Dyalog APL version 18.2.

## Initialisation

### From inside APL

```apl
2⎕FIX'file://path/to/Run.aplf'
Run⊂'path/to/your.ipynb'
```

Optionally, a left argument can be given. If `¯1` then the whole document will be run non-interactively. If using the Windows IDE, a positive number can be given which will delay that many seconds before each keypress, and optionally, a second number can be given which is a standard deviation to randomise the delay.

### From outside APL

```shell
dyalog LOAD="path/to/Run.aplf"
```

The system will use the first-found .ipynb file adjacent to Run.aplf unless the environment variable `DYALOG_JUPYTER_RUN` has been set to a Jupyter Notebook document filename.

On Windows, you can also right-click on Run.aplf or its containing folder and select "Run with Dyalog".

## Usage

* Press <kbd>Enter</kbd> to proceed to the next step.

* Enter `→` cease rendering immediately.

* Enter any number of `←`s to go back that many steps.

* Enter `∘` to stop and suspend the execution of `Run` (for debugging purposes)

## Limitations

Markdown rendering is obviously very simplified, since there's no rich text capability in the APL session. Markdown blocks are indicated by an outline. Headings (`#`s) are rendered like plain text, but slightly indented, and code blocks are prefixed with a language marker.

Many system functions are not supported, and some have limited functionality or return simplified messages. The following system functions *are* at least partially supported:

* `)CLEAR`

* `)CMD` 

* `)COPY`

* `)ED`

* `)FNS`

* `)LOAD`

* `)NS`

* `)OBJECTS`

* `)OBS`

* `)OFF`

* `)SH`

* `)TID`

* `)VARS`

* `)WSID`

* `)XLOAD`
