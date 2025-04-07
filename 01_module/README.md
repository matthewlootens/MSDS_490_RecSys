# Module 1

## Recommender Systems for mHealth 
1. How would you deploy a recommender system to serve your employees or customers?

I am interested in thinking about how recommender systems can be understood as a form of information retrieval and management.  As a public health researcher, I am particularly interested in exploring possible applications of utilizing recommender systems in health care and in public health interventions to improve population health and address health disparities. Though some of Northwestern's MSDS coursework, I've also become interested in exploring future entrepreneurial career pathways for developing digital and mobile health applications that use analytics and AI.

2. What problem would you solve using this recommender system to increase employee productivity, improve retention (customer and/or employee), increase revenue, or increase profits?
   
The end goal would be, of course, to improve individual and population health and reduce pre-existing disparities in population health. Potential "items" that would recommended could include healthy meal options, exercise routines, and health education documents.

3. How would you collect the underlying data needed to make recommendations?

Health data for individuals are readily available in the form of electronic medical records (EHR), though these are subject to a variety of regulatory oversight (e.g., the Health Insurance and Portability Act [US Department of Health and Human Services 2024]). Public health surveillance data are also readily collected by a variety of federal, state, and local health departments.  These data sources, while rich, could easily be combined with wearable health devices, such as activity trackers that record users' activity in real time.  Such devices are not subject HIPAA regulations (Katuska 2018) and provide much more granular data.

4. What type of data pipeline would you need to ensure your recommendations stay current?

Ingesting and incorporation of EHR and population-level surveillance data could be done offline, especially as this data does not change rapidly and only a discrete points. But despite infrequent updates, the data is rich across a population and will certainly require thoughtful algorithms for computational complexity. Wearable data trackers will need to be uploaded periodically to central servers through connection to smart phones. These minute- and second-level epoch data will need to be filtered and preprocessed for use in the recommender system. 

5. How would you deal with data from new employees and/or new customers?

New customers' data would be ingested and processed like all other data. Because this recommender system would be health-related, accuracy would be more important than novelty or diversity (Li et al. 2024, 24).  As a result, online processing would not be as important in this application.

## References

Katuska, John T. 2018. “Wearing Down HIPAA: How Wearable Technologies Erode Privacy Protections.” The Journal of Corporation Law 44 (2): 385–401.

Li, Dongsheng, Jianxun Lian, Le Zhang, Kan Ren, Tun Lu, Tao Wu, and Xing Xie. 2024. Recommender Systems: Frontiers and Practices. Singapore: Springer Nature Singapore. https://doi.org/10.1007/978-981-99-8964-5.

US Department of Health and Human Services. 2024. “HIPAA for Professionals.” July 19, 2024. https://www.hhs.gov/hipaa/for-professionals/index.html.