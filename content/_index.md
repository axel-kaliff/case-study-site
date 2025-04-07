---
title: 'Can Visuo-motor Policies Benefit From Random Exploration Data?'
date: 2023-10-24
type: landing

design:
  spacing: "2rem"

sections:

  - block: markdown
    content:
      text: |
        <center>
        <div class="custom-hero">
          <h3>Can Visuo-motor Policies Benefit From Random Exploration Data? A Case Study on Stacking</h3>
          <p id="custom-authors">Shutong Jin*, Axel Kaliff*, Ruiyu Wang, Muhammad Zahid, Florian T. Pokorny</p>
        </div>
          <a
            href="https://arxiv.org/abs/2503.23571"
            class="inline-block rounded border px-5 py-2 font-semibold transition
            md:ml-4 px-4 py-1.5 text-sm
            border-black  hover:bg-black dark:hover:bg-white dark:hover:text-black hover:text-white dark:border-white dark:text-white dark:hover:bg-white
            lg:inline-block">
            Read the Paper
          </a>
        </center>
#           <a href="https://github.com/ShutongJIN/CloudGripper_Stack_1k" class="mt-3 inline-flex items-center text-white bg-primary-700 hover:bg-primary-800 focus:ring-4 focus:ring-primary-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:focus:ring-primary-900">
#            Explore the Code
#            <svg class="ml-2 -mr-1 w-5 h-5" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd"></path></svg>
#          </a>


    design:
      css_class: "dark"
      css_style: |
        .custom-hero {
          padding: 4rem 2rem;
          text-align: center;
          color: white;
        }
        .custom-hero h3 {
          font-size: 1.5rem;
          font-weight: 500;
          margin-bottom: 1rem;
        }
        #custom-authors {
          font-size: 1rem !important; /* Default font size */
          margin-bottom: 1.5rem;
        }
        @media (min-width: 1024px) {
          .custom-hero .custom-authors {
            font-size: 0.25rem !important;
          }
        }
        .buttons {
          display: flex;
          justify-content: center;
          gap: 1rem;
          margin-top: 2rem;
        }
        .primary-button, .secondary-button {
          display: inline-block;
          padding: 0.7rem 1.5rem;
          border-radius: 20px;
          font-weight: 500;
          text-decoration: none;
          transition: all 0.3s ease;
          border: 1px solid #6a0dad;
        }
        .primary-button {
          background-color: #6a0dad;
          color: white;
        }
        .secondary-button {
          background-color: rgba(106, 13, 173, 0.7);
          color: white;
        }
        .primary-button:hover, .secondary-button:hover {
          transform: translateY(-2px);
          box-shadow: 0 4px 8px rgba(106, 13, 173, 0.3);
          background-color: #7b1fa2;
        }
      background:
        color: "navy"
        image:
          filename: matrix.gif
          filters:
            brightness: 0.11

  - block: stats
    content:
      items:
        - statistic: "13k+"
          description: |
            Real-world episodes
        - statistic: "750+"
          description: |
            Hours of labeled activity
        - statistic: "1200+"
          description: |
            Real-world policy evaluations
    design:
      css_class: "bg-gray-100 dark:bg-gray-900"
      spacing:
        padding: ["1rem", 0, "1rem", 0]


  - block: markdown
    content:
      text: |
        ## Motivation
        Visuo-motor policies for robotic manipulation have long faced scalability challenges in collecting human demonstrations. The high cost of human labor and reliance on teleoperation systems pose substantial barriers to data collection in new environments. This motivates us to focus on a scalable yet often overlooked data source—random exploration data, collected within the target task’s environment, which might be a potential add-on for human demonstrations. However, its lack of task-specific information and the inherent unstructured nature of such data greatly complicates its practical utilization. This leads us to investigate the following question: __Can Visuo-motor Policies Benefit from Random Exploration Data?__

    design:
      css_class: "light"
      css_style: |
        h2 {
          font-size: 2rem;
          margin-bottom: 1rem;
        }
        p {
          font-size: 1rem;
          line-height: 1.6;
        }
      background:
        color: "white"



  - block: markdown
    content:
      text: |
        ## Overview
        We examine two paradigms for leveraging random exploration data in visuo-motor policy learning:
        - **Paradigm I** evaluates the use of random exploration video frames through three self-supervised pre-training objectives: reconstruction, contrastive, and distillation loss.
        - **Paradigm II** evaluates the effectiveness of random motor commands for autonomous data collection within a fully automated staged learning framework.

        The dataset presented in this work includes over **750 hours** of robot activity data.

    design:
      css_class: "bg-gray-100 dark:bg-gray-900"
      css_style: |
        h2 {
          font-size: 2rem;
          margin-bottom: 1rem;
        }
        p {
          font-size: 1rem;
          line-height: 1.6;
        }
      background:
        color: "white"

    design:
      css_class: "light"
      css_style: |
        h2 {
          font-size: 2rem;
          margin-bottom: 1rem;
        }
        p {
          font-size: 1rem;
          line-height: 1.6;
        }
      background:
        color: "white"


  - block: cta-image-paragraph
    id: solutions
    content:
      items:
        - title: Random Video Frames for Visual Pre-training
          text: |
            Random exploration video frames are used for self-supervised visual pre-training. The resulting pre-trained visual encoder is then applied and evaluated in a visuo- motor policy for a new task.
          image: structureA.png
          button:
            text: CloudGripper-Push-1K Dataset
            url: "https://github.com/cloudgripper/cloudgripper-push-1k"
        - title: Random Motor Commands for Staged Learning
          text: |
            Data episodes are generated via random motor commands, with a detector using a custom bottom camera that views the scene from below through a transparent base plate to automatically label episodes as successful or failed. The successful episodes are used to train a policy for autonomous data collection.
          image: structureB.png
          button:
            text: Code will be open-sourced after paper acceptance
            url: "#"
    design:
      css_class: "bg-gray-100 dark:bg-gray-900"
      spacing:
        padding: ["2rem", "2rem", "2rem", "2rem"]

  - block: features
    id: features
    content:
      title: Comparative Analysis of Self-Supervised Objective Functions
      text: GIFs below show FullGrad saliency maps for models with different pre-training objectives and datasets. All models shown use the ViT-Small architecture. Results of all models and dataset compared in this work can be found in the [paper](https://arxiv.org/abs/2503.23571).
      items:
        - name: MoCo (Contrastive Loss)
          description: |
            ![Alt text](moco_vit_small_RM_cam.gif)
        - name: DINO (Distillation Loss)
          description: |
            ![Alt text](dino_vit_small_RM_cam.gif)
        - name: MAE (Reconstruction Loss)
          description: |
            ![Alt text](mae_vit_small_RM_cam.gif)
    design:
      css_class: "bg-white dark:bg-gray-800"
      spacing:
        padding: ["2rem", "2rem", "1rem", "1rem"]

  - block: markdown
    content:
      text: |
       We find that models pre-trained with MoCo objective outperform both MAE and DINO by a significant margin when trained on random exploration data. It can be seen that the activations of MoCo ViT-Small concentrate mainly in the task area. In contrast, the activations of poor-performing MAE ViT-Small and DINO ViT-Small focus on the background and exhibit dispersed activations when trained on random exploratin data. 
      design:
      css_class: "bg-white dark:bg-gray-900"
      spacing:
        padding: ["0.1rem", "0.1rem", "5rem", "0.1rem"]


  - block: markdown
    content:
      text: |
        ## Overview of Results
        -  **Paradigm I**: We identify MoCo with a ViT-Small architecture as an effective approach for visual pre-training leveraging random exploration video frames, though its performance is highly dependent on object initial positions.
        - **Paradigm II**: We find that autonomous data collection policies exhibit a strong distributional bias regarding the position of successful episodes in the workspace; however, incorporating data collected via random motor commands introduces balancing randomness, mitigating the distributional bias. Furthermore, our findings suggest that enforcing an even data distribution when composing data across stages and employing separate subtask policies may enable fully autonomous collection of sequential tasks.
    design:
      css_class: "bg-gray-100 dark:bg-gray-900"
      spacing:
        padding: ["2rem", "2rem", "2rem", "2rem"]

  - block: markdown
    content:
      text: |
        ## CloudGripper-Stack-750 Dataset
        ![Alt text](matrix.gif)
        The dataset comprises over **750 hours** of robot activity data—including **400 successful** and **12,000 failed** episodes—collected autonomously using the CloudGripper testbed. This comprehensive collection is provided as a resource for research on visuo-motor policy development. The dataset will be open-sourced after paper acceptance.
    design:
      css_class: "light"
      css_style: |
        h2 {
          font-size: 2rem;
          margin-bottom: 1rem;
        }
        p, a {
          font-size: 1rem;
          line-height: 1.6;
        }
      background:
        color: "white"





  - block: cta-card
    content:
      title: Collected Using CloudGripper
      text: |
          In this study, the **CloudGripper robotic testbed** was employed to remotely and autonomously collect a large dataset of real robot data, train policies, and conduct evaluations with **minimal human intervention** via cloud services. Researchers interested in utilizing CloudGripper are encouraged to explore the **open-source dataset** and **data collection pipeline**.
      button:
        text: CloudGripper Github
        url: "https://github.com/cloudgripper"
    design:
      card:
        css_class: "bg-primary-700"
        css_style: "color: white; text-align: center; padding: 2rem;"

  - block: markdown
    content:
      text: |
        ### Acknowledgements
        **Equal contribution.** The authors are with the School of Electrical Engineering and Computer Science, KTH Royal Institute of Technology. This work was partially supported by the Wallenberg AI, Autonomous Systems and Software Program (WASP), funded by the Knut and Alice Wallenberg Foundation. The computations were enabled by the supercomputing resource Berzelius provided by the National Supercomputer Centre at Linköping University and the Knut and Alice Wallenberg Foundation, Sweden.
        ![Alt text](kth-logo.png)
    design:
      css_class: "light"
      css_style: |
        h2 {
          font-size: 2rem;
          margin-bottom: 1rem;
        }
        p, a {
          font-size: 1rem;
          line-height: 1.6;
        }
      background:
        color: "white"
---

