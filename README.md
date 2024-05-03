# Visuomotor model of the left Superior Colliculus

>Model created by Kris Jensen (University of Cambridge) as Jupyter notebook in colab.

Three-layer network model of the left SC composed of a static spatial receptive field (ssRF) layer, a direction selective (DS) layer and a motor layer, of 500 neurons each. The connectivity between these layers was strictly top down and constrained by experimentally observed connectivity, visual tuning and sensorimotor alignment. We also incorporated in the model the experimental observation that orientation and direction selective neurons in the superficial layer of the SC are arranged in a centripetal pattern. We used this 3-layer network to systematically compare how a direct retino-premotor pathway (“kinetic pathway”), relying exclusively on kinetic information of the visual target, or an indirect retino-premotor pathway (“static pathway”), relying on ssRF activation, would allow interception of moving and static targets.

In the model engaging the kinetic pathway, a moving target activates neurons in the DS layer that are tuned to the radial component of target motion. In turn, these DS neurons excite those motor units with opposite (anti-aligned) preferred movement vector. This operating regime supports fast interception of moving targets as long as the motion of the target includes a radial component (e.g. target moving towards the agent). When quantifying the accuracy of this model by the Euclidean distance to the target at the end of each simulated trial, we found it to be comparable to that of a canonical static model that first engages ssRF neurons. Importantly, a visuo-motor anti-alignment was the only alignment supporting target interception and is required when either of the two pathways is engaged. When we consistently shifted the alignment between the direction selective layer and the motor layer, the agent failed to reach the target. 

The model is also compatible with reaching static targets. In this scenario, the location of the visual stimulus would drive the appropriate neurons in the ssRF layer. The ssRF neurons then feed into the DS layer according to the topographic constraints dictated by concentricity, and the DS neurons activate the motor neurons on the basis of the kinetic alignment constraints described above.

Because our network is constrained by the concentricity of the visual features encoded, we found that the kinetic pathway prioritises the interception of targets with the highest chances of success by ignoring targets moving away from the agent. This feature of the model improved energy efficiency as measured by the total amount of movement produced over all attempted interceptions. Although our results indicate a preferential bias to fast, energy efficient target interception, the model is also consistent with tracking and reaching of eccentric targets if the retinotopic layer can produce enough drive, in agreement with our finding of a strong inhibitory gate primarily impinging on this pathway and affecting direction and orientation selectivity.


>[!NOTE]
>* conc = True/False indicates concentric/retinotopic and is used to switch between "kinetic" and "static" pathways.
>* The "kinetic" model in the paper is here referred to as "concentric" as it relied on the concentric movement of the target to elicit movement.
>* The "static" model in the paper is here referred to as "retinotopic" as it uses the retinotopic location at time t of the target to produce movement.
>* The range of motion of the agent was restricted to realistic field of view of the mouse and head movements (that is, it would not be possible for the head to rotate 360 degrees)

# Requirements
- Packages: matplotlib, numpy
- System: any operating system
- Installation: no need for installation, can be ran in google.colab

All results included in Figure 4 of the manuscript can be reproduced using this code.
