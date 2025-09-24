---
# Leave the homepage title empty to use the site title
title: ''
date: 2022-10-24
type: landing

design:
  # Default section spacing
  spacing: '6rem'

sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      text: ''
      # Show a call-to-action button under your biography? (optional)
      button:
        text: Download CV
        url: uploads/resume.pdf
      headings:
        about: ''
        education: ''
        interests: ''
    design:
      # Apply a gradient background
      css_class: hbx-bg-gradient
      # Avatar customization
      avatar:
        size: medium # Options: small (150px), medium (200px, default), large (320px), xl (400px), xxl (500px)
        shape: circle # Options: circle (default), square, rounded
  # - block: markdown
  #   content:
  #     title: '📚 My Research'
  #     subtitle: ''
  #     text: |-
  #       Use this area to speak to your mission. I'm a research scientist in the Moonshot team at DeepMind. I blog about machine learning, deep learning, and moonshots.

  #       I apply a range of qualitative and quantitative methods to comprehensively investigate the role of science and technology in the economy.

  #       Please reach out to collaborate 😃
  #   design:
  #     columns: '1'
  - block: markdown
    id: 科研项目
    content:
      title: '科研项目'
      subtitle: ''
      text: |-
        1. 2024年度博士后创新人才支持计划，项目负责人，浙大土木学科首位入选者，No. BX20240320
        2. 国家重点研发计划青年科学家项目，任务负责人，No. 2024YFB3715100
    design:
      columns: '1'
  - block: markdown
    id: 研究成果
    content:
      title: '研究成果'
      subtitle: ''
      text: |-
1. Yin X, Li Q*, Chen B, Xu S. An improved calibration of Karagozian & Case concrete/cementitious model for strain-hardening fibre-reinforced cementitious composites under explosion and penetration loadings. Cement and Concrete Composites. 2023;137:104911.  doi: 10.1016/j.cemconcomp.2022.104911
2. Yin X, Li Q*, Xu X, Chen B, Guo K, Xu S. Investigation of continuous surface cap model (CSCM) for numerical simulation of strain-hardening fibre-reinforced cementitious composites against low-velocity impacts. Composite Structures. 2023;304:116424.  doi: 10.1016/j.compstruct.2022.116424
3. Yin X, Li Q*, Wang Q, Chen B, Shu C, Xu S. Mesoscale numerical investigation of dynamic spalling fracture in toughness concrete. International Journal of Mechanical Sciences. 2024;264:108826.  doi: 10.1016/j.ijmecsci.2023.108826
4. Yin X, Li Q*, Wang Q, Chen B, Xu S. Near range explosion resistance of UHPFRC panels in wide scaled distances: Experimental study and stochastic numerical modelling. International Journal of Impact Engineering. 2024;192:105028.  doi: 10.1016/j.ijimpeng.2024.105028
5. Yin X, Li Q*, Wang Q, Reinhardt H-W, Xu S. The double-K fracture model: A state-of-the-art review. Engineering Fracture Mechanics. 2023;277:108988.  doi: 10.1016/j.engfracmech.2022.108988
6. Yin X, Li Q*, Wang Q, Chen B, Xu S. Experimental and numerical investigations on the stress waves propagation in strain-hardening fiber-reinforced cementitious composites: Stochastic analysis using polynomial chaos expansions. Journal of Building Engineering. 2023;74:106902. doi: 10.1016/j.jobe.2023.106902
7. Hao Y#, Yin X#, Li Q*, Quan G, Xu S. Dynamic direct tensile behaviour of high-strength strain-hardening fibre-reinforced cementitious composites: Rate dependence, inertial effect, and ductile-brittle transition. International Journal of Impact Engineering. 2025; 202:105309. doi: 10.1016/j.ijimpeng.2025.105309
8. Li Q, Yin X, Huang B*, Luo A, Lyu Y, Sun C, Xu S. Shear Interfacial Fracture of Strain-Hardening Fiber-Reinforced Cementitious Composites and Concrete: A Novel Approach. Engineering Fracture Mechanics. 2021; 253:107849. doi: 10.1016/j.engfracmech.2021.107849
9. Li Q, Yin X, Huang B*, Zhang Y, Xu S. Strengthening of the Concrete Face Slabs of Dams Using Sprayable Strain-Hardening Fiber-Reinforced Cementitious Composites. Frontiers of Structural and Civil Engineering, 2022; 16(2):145–60. doi: 10.1007/s11709-022-0806-4
10. 银星, 李庆华. 基于机器学习的超高韧性水泥基复合材料板在近场爆炸荷载作用下的损伤预测. 工程力学. doi: 10.6052/j.issn.1000-4750.2024.10.0791
11. 李庆华, 刘雪涵, 银星*, 徐世烺. 循环压缩作用下高强高韧混凝土的力学性能与损伤演化模型研究. 东南大学学报(自然科学版).
12. 李庆华, 银星, 郭康安, 徐世烺*. 超高韧性水泥基复合材料与活性粉末混凝土界面剪切强度试验研究. 工程力学 , 2022, 39(8):232–44. doi: 10.6052/j.issn.1000-4750.2021.05.0355
    design:
      columns: '1'
  - block: collection
    id: papers
    content:
      title: Featured Publications
      filters:
        folders:
          - publications
        featured_only: true
    design:
      view: article-grid
      columns: 3
  - block: collection
    content:
      title: Selected Publications
      text: ''
      filters:
        folders:
          - publications
        exclude_featured: true
    design:
      view: citation
  # - block: collection
  #   id: talks
  #   content:
  #     title: Recent & Upcoming Talks
  #     filters:
  #       folders:
  #         - events
  #   design:
  #     view: card
  # - block: collection
  #   id: news
  #   content:
  #     title: Recent News
  #     subtitle: ''
  #     text: ''
  #     # Page type to display. E.g. post, talk, publication...
  #     page_type: blog
  #     # Choose how many pages you would like to display (0 = all pages)
  #     count: 5
  #     # Filter on criteria
  #     filters:
  #       author: ''
  #       category: ''
  #       tag: ''
  #       exclude_featured: false
  #       exclude_future: false
  #       exclude_past: false
  #       publication_type: ''
  #     # Choose how many pages you would like to offset by
  #     offset: 0
  #     # Page order: descending (desc) or ascending (asc) date.
  #     order: desc
  #   design:
  #     # Choose a layout view
  #     view: card
  #     # Reduce spacing
  #     spacing:
  #       padding: [0, 0, 0, 0]
  - block: cta-card
    demo: true # Only display this section in the Hugo Blox Builder demo site
    content:
      title: 👉 Build your own academic website like this
      text: |-
        This site is generated by Hugo Blox Builder - the FREE, Hugo-based open source website builder trusted by 250,000+ academics like you.

        <a class="github-button" href="https://github.com/HugoBlox/hugo-blox-builder" data-color-scheme="no-preference: light; light: light; dark: dark;" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star HugoBlox/hugo-blox-builder on GitHub">Star</a>

        Easily build anything with blocks - no-code required!

        From landing pages, second brains, and courses to academic resumés, conferences, and tech blogs.
      button:
        text: Get Started
        url: https://hugoblox.com/templates/
    design:
      card:
        # Card background color (CSS class)
        css_class: 'bg-primary-700'
        css_style: ''
---
