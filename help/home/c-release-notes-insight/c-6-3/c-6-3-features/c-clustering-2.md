---
description: The Cluster Builder now includes a KMeans++ algorithm (only the KMeans algorithm was previously supported) that uses a faster approach to finding centers for an expedited cluster-generation process.
seo-description: The Cluster Builder now includes a KMeans++ algorithm (only the KMeans algorithm was previously supported) that uses a faster approach to finding centers for an expedited cluster-generation process.
seo-title: Clustering 2.0
title: Clustering 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
---

# Clustering 2.0{#clustering}

The Cluster Builder now includes a KMeans++ algorithm (only the KMeans algorithm was previously supported) that uses a faster approach to finding centers for an expedited cluster-generation process.

## KMeans Algorithms {#section-92383a1be1d6402c95a25c902e90b850}

In the [Cluster Builder](https://marketing.adobe.com/resources/help/en_US/insight/client/c_visitor_cluster.html), you can now select **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** to select algorithms when defining clusters.

* **[!UICONTROL KMeans]**. This algorithm uses canopy clustering to define the centers of the cluster. 
* **[!UICONTROL KMeans++]**. This algorithm expedites cluster building when running against large sets of data.

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++ is an improved implementation of KMeans clustering algorithm because it provides better initialization of initial k centers. (The original KMeans algorithm chooses initial centers randomly.) KMeans++ selects the first center randomly. The remaining k-1 centers will be chosen one by one based on the distance a data point is to the closest existing center. The furthest data points have a better chance to be chosen as a new center than nearby data points. After the initial center is chosen, the procedure is performed exactly the same as the original KMeans clustering.

The workflow for KMeans++ is exactly the same as the workflow for KMeans clustering, except that you need to select **Options** > **Algorithm** > **KMeans++** in the cluster builder.

>[!NOTE]
>
>Each DPU runs its own KMeans++ procedure on its own data portion. If the DPU has enough available memory (the ratio is configurable in the PAServer.cfg file), then the data of those involved variables will be brought into memory. The remaining k-1 initial center selection and converging iterations all happen in memory, which is faster than the previous KMeans clustering.

