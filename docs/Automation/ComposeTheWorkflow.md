# Task 2: Compose The Workflow

Switch to the **Designer** tab.
On the left, under Tools, you can see three subtabs:

* **Tasks**: Contains the list of system and non-system (custom) tasks by category. A task is an atomic action you can perform against a target (i.e. create server profile, deploy new virtual machine, etc.)

* **Workflows**: Contains the list of workflows that can be used as tasks (nested workflows) within a larger workflow. In this case, workflow inputs are treated as task inputs and workflow outputs are treated as task outputs

* **Operations**: At the moment, Intersight automation offers three special tasks:
    * **Conditional Task**: This task allows the creation of multiple branches that can be followed at execution runtime based on configured condition. An example would be taking different path based on a task output or a user choice
    * **Parallel Loop**: This is a container task, whatever task gets dropped into this task, it will be execute n times in a parallel fashion. Where n is a configurable integer or can be rendered with a configuration template dynamically
    * **Serial Loop**: This is a container task, tasks within this task will be executed sequentially until a counter expires or a configured condition is met. An example would be: "execute all tasks serially until the output of this task is "foo"

Move to the **Tasks** subtab.

Search the task **New Server Profile from Template** and drag it to the canvas as shown below:

![Compose The Workflow 1](./ComposeTheWorkflow1.png "Compose The Workflow 1")

Click the task and note a new panel has opened on the right, as shown below:

![Compose The Workflow 2](./ComposeTheWorkflow2.png "Compose The Workflow 2")

These are the properties of the task. Each task comes with **Input, Outputs** and can handle (use or manipulate) **Variables**.

Under **General**, you can set the task name and a description. For this lab, we will leave it as it is.

Move to the **Inputs** tab.

You can see a list of inputs, specific for this task. Each input can be mandatory or optional

![Compose The Workflow 3](./ComposeTheWorkflow3.png "Compose The Workflow 3")

This specific task has only one mandatory input, which is **Source Profile Template**, basically what is the template we will derive a server profile from.
Let's go ahead and assign or **Map**, a value to this input. For the **Source Profile Template** input, click the **Map** button.

The form defaults to a **Static Value** type of mapping. However, we generally have three different types of mappings. Let's explore them:

![Compose The Workflow 4](./ComposeTheWorkflow4.png "Compose The Workflow 4")

* **Static Value**: Assigns a value that will always be honoured at every execution. Based on the input type, you have the possibility to query the Intersight database (like in this case, where you can pull the list of all server profile templates configured for your account), set an arbitrary text string, set a number (Integer), etc.

* **Direct Mapping**: Maps the value to either a Workflow Input, another Task output (which has to be positioned in the canvas before the current task), a Workflow Variable or an Environment Variable

* **Advanced Mapping**: Is a way for advanced users to write Go template code in order to map values dynamically based on custom code. As mentioned, this is an advanced topic and out of scope for this lab.

For this input, we will go ahead and perform a static mapping.
Under **Type of Mapping** select **Static Value**.

Click on **Select Source Profile Template** to get the list of the configured profile templates as shown in the picture below.

Select your student profile template “SRVX-ServerProfileTemplate” then click **Select** in the bottom right corner.

![Compose The Workflow 5](./ComposeTheWorkflow5.png "Compose The Workflow 5")

Click **Map** in the bottom right corner to confirm.

Let's stop for a second and explore the anatomy of a task.
You know that each task has inputs, outputs, the possibility to consume variables, a name and a description.
Each task has also two exit conditions as you can see in the screenshot below:

![Compose The Workflow 6](./ComposeTheWorkflow6.png "Compose The Workflow 6")

By connecting these green and red dots, you can create paths based on your use case, for instance you can decide to execute a specific task if a previous task fails.
Eventually, the workflow either fails or succeeds based on the outcomes of all tasks.

Now that we instructed the workflow to create a server profile out of a template, we want to map the created template to a server.
In the **Tools** panel on the left side, search for the task **Set Server to Server Profile**. As soon as you start dragging the task under the **New Server Profile from Template** task, a green plus sign will appear. If you release the task over the plus sign, it will automatically be connected to the success line (the green line) of the **New Server Profile from Template** task as shown below:

![Compose The Workflow 7](./ComposeTheWorkflow7.png "Compose The Workflow 7")

Click on the **Auto Align Workflow** button to automatically align the tasks:

![Compose The Workflow 8](./ComposeTheWorkflow8.png "Compose The Workflow 8")

Before moving forward with the inputs, let's see how Intersight validates and saves the workflows.

Click the **Save** button in the top right corner.
When you **Save** a workflow, Intersight will perform two actions:

* Save the workflow definition
* Validate the workflow

The green banner indicates the workflow has been saved:

![Compose The Workflow 9](./ComposeTheWorkflow9.png "Compose The Workflow 9")

However, you can also see there are 2 errors found! and the workflow transitioned into the **Invalid** state:

![Compose The Workflow 10](./ComposeTheWorkflow10.png "Compose The Workflow 10")