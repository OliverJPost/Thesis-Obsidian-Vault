---
aliases: ["Han et al. (2024) Autoencoding tree for city generation and applications"]
tags: [City generation, Real-world city datasets, Tree-structured neural network, Urban planning applications]
year: 2024
---
# Autoencoding tree for city generation and applications [📖](zotero://select/library/items/UUAEHDPP)

> [!abstract]-
> 
> City modeling and generation have attracted an increased interest in various applications, including gaming, urban planning, and autonomous driving. Unlike previous works focused on the generation of single objects or indoor scenes, the huge volumes of spatial data in cities pose a challenge to the generative models. Furthermore, few publicly available 3D real-world city datasets also hinder the development of methods for city generation. In this paper, we first collect over 3,000,000 geo-referenced objects for the cities of New York, Zurich, Tokyo, Berlin, Boston, and several other large cities. Based on this dataset, we propose AETree, a tree-structured auto-encoder neural network, for city generation. Specifically, we first propose a novel Spatial-Geometric Distance (SGD) metric to measure the similarity between building layouts and then construct a binary tree over the raw geometric data of the building based on the SGD metric. Next, we present a tree-structured network whose encoder learns to extract and merge spatial information from the bottom-up iteratively. The resulting global representation is reversely decoded for reconstruction or generation. To address the issue of long-dependency as the level of the tree increases, a Long Short-Term Memory (LSTM) Cell is employed as a basic network element of the proposed AETree. Moreover, we introduce a novel metric, Overlapping Area Ratio (OAR), to quantitatively evaluate the generation results. Experiments on the collected dataset demonstrate that the proposed model outperforms baseline models, such as LayoutTransformer and LayoutVAE, in terms of key metrics. Specifically, the proposed model achieves a Jensen–Shannon Divergence (JSD) of 0.0033, compared to 0.0041 and 0.0061 for LayoutTransformer and LayoutVAE, respectively. Similarly, for the Overall Accuracy Rate (OAR), the proposed model scores 1.66, significantly better than 28.24 and 19.01 for the baseline models Furthermore, the latent features learned by AETree can serve downstream urban planning applications. Project webpage is available at https://ai4ce.github.io/RealCity3D.
> 

> [!quote]- Citations
> 
> ```query
> content: "@hanAutoencodingTreeCity2024" -file:@hanAutoencodingTreeCity2024
> ```

%% begin notes %%
![[image.png | canvas-top]]
## Permanent notes
importance::undefined
completed::false
### Initial thoughts:


### Relations:


### Summary


%% end notes %%
## Reading notes
%% begin annotations %%

%% end annotations %%



%% Import Date: 2024-05-01T00:52:42.815+02:00 %%
