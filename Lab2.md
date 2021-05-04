# Tutorial: 2 Understanding ROS Topics, Node and Messages

## ROS Topics

The information in ROS is called a **topic**. A topic defines the types of messages that will be sent concerning that topic.

### **Using rqt_graph**

rqt_graph creates a dynamic graph of what's going on in the system. It shows the nodes and topics currently running.

```
$ rosrun rqt_graph rqt_graph
```

![lab2_1](./lab2_1.png)

The turtlesim_node and the turtle_teleop_key node are communicating with each other over a ROS Topic named `/turtle1/command_velocity`.

### **Introducing rostopic**

_(Version Information: we are currently ROS hydro Or Later version)_

The rostopic tool allows you to get information about ROS topics.
following are some sub-commands for **rostopic**:

```
rostopic bw     // bandwidth used by topic.
rostopic echo   // print messages to screen
rostopic hz     // display publishing rate of topic
rostopic list   // print information about active topics
rostopic pub    // publish data to topic
rostopic type   // print topic type
```

following are some applied examples:

-   rostopic echo shows the data published on a topic.

    ```
    $ rostopic echo /turtle1/cmd_vel
    ```

    you should now see the following when you press the up key:

    ![lab2_echo](./lab2_echo.png)

    ![lab2_rqtg](./lab2_rqtg.png)

    As you can see, new node (**red color**), `rostopic echo`, is now also subscribed to the **turtle1/command_velocity** topic.

-   rostopic list returns a list of all topics currently subscribed to and published.

    ```
    $ rostopic list -h
    ```

    ![lab2_list](./lab2_list.png)
