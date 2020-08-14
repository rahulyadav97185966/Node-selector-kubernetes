# Node-selector-kubernetes

Example of Production Scenario : Suppose we have project and we have to deploy that project but first we have to test that project, how that project works and how things are working on nodes. so we have different types of nodes where we can deploy it so we label one node or we create a node for testing so we have to select node for the testing and one is for actual production scenario. So we have to select Node Here.

First in lab we cannot create a pod on the master or controlpane in online OKD so we change soome attributes from nodes file  
 
    #kubectl edit nodes controlplane : delete taints line from the code (three lines)
    # Now we can launch the pod on the master or controlplane
    # now we have to add labels to the nodes
    # kubectl get nodes --show-labels : this commands shows the labels of the nodes.
    #kubectl label node controlplane type=production
    #kubectl label node node01 type=testing
    #vi apache.yml : copy the apache file given in repo and paste it
    #kubectl create -f apache.yml
    #kubectl get pods -w
    #kubectl get pods -o wide : now you can see the pod is running on the tesing i.e node01
    #vi mario.yml : copy the mario file given in repo and paste it
    #kubectl create -f mario.yml
    #kubectl get pods -w
    #kubectl get pods -o wide : now you can see the pod is running on the production i.e controlplane or master
    
    
  
