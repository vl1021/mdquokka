## Overview

This project uses PlantUML to create diagrams directly within Markdown files. PlantUML is a powerful tool for generating UML diagrams from plain text descriptions. There are two options to include the diagrams in your markdown.

### Option 1 : PlantUML Code Block in Markdown
To include a PlantUML diagram in your Markdown file, you use a fenced code block with the language identifier plantuml. You can also add attributes like caption, width and height to customize the diagram.

#### Using Handlebars Expressions in PlantUML Code Blocks
You can use Handlebars expressions in your PlantUML code blocks to dynamically generate diagrams based on variable data.

#### Example
<pre>
<h4>```{.plantuml caption="This is my image caption, created by PlantUML" width=450 }</h4>
@startuml
skinparam ConditionEndStyle hline
  
start
:receive txState, bleState,
authStatus, and persistenceError;
:use CgmEngineTransientStorage;
if (persistenceError exists) then ( yes )
  if (persistenceError is unrecoverableSqlError) then ( yes )
    :return blocked([unrecoverableError]);
  else ( no )
    :return blocked([recoverableError]);
  endif
  stop
else ( no )
  :request diskSpace state;

<h4>{{#if features.DiskSpace.Critical}}</h4>
  if (diskSpace is critically low) then ( \n yes )
    :add diskSpaceCritical to blockingReasons;
  else ( no )
  endif
<h4>{{/if}}</h4>
endif
:request timeLoss state\nand battery state;
if (timeLoss is active) then (\n yes )
  :add timeLoss to warnings;
else ( no )
  :modelStorage.clearTimeLossWarning();
endif
<h4>{{#if features.DiskSpace.LowVeryLow}}</h4>
if (diskSpace is <b>low</b> or <b>very low</b>) then (\n yes )
  :add diskSpace(low or veryLow) to warnings;
else ( no )
  :modelStorage.clearDiskSpaceWarning();
endif
<h4>{{/if}}</h4>
:return operational(txState, authStatus, warning);
stop
  
@enduml
```
</pre>
### Option 2
