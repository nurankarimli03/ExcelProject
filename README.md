Telekom datası ilə tariflərin (kampaniyaların) və istifadəçilərin analizi 
Sizə müştərilərdən (customer), tariflərdən (campaign) və müştərilərin kampaniyalara ilk qoşulma 
və alış tarixləri barədə data verilib. 
1. “Cohort” adlı səhifə yaradaraq:  
Müştərilərin kampaniyalara ilk qoşulma tarixlərindən asılı Cohort analizi edin. Alınmış hesabata 
istənilən kampaniya üzrə baxmaq mümkün olmalıdır.  
Telekom datasına nəzər saldıqda 3 səhifədən, customer, campaign, data ibarət olduğu görünür. 
İlk olaraq, cohort analizini etmək üçün data adlı səhifədə difference adında sütun yaradılır. 
Məqsəd join_date və buy_date arasında olan ay fərqini tapmaqdır. Bu öz növbəsində məs, 
yanvar ayında kampaniyaya qoşulan müştəri sonrakı hansı aylarda alış etmişdir onu göstərir. 
Difference sütunu yaradıldıqdan sonra yeni bir Excel iş kitabı açılır(layihənin bütün şərtləri bu iş 
kitabındada yerinə yetiriləcək). Datalar power query-də yoxlanıldıqdan sonra əlaqə(connection) 
yaradılır, data modelə əlavə olunur və daha sonra power pivot-da 3 cədvəl arasında 
əlaqələr(birin(customer, compaign)-çoxa(data)) və pivot table yaradılır. Cohort analizinin əsas 
məqsədi, müəyyən bir qrupun zaman içərisində davranışlarını izləyərək, həmin qrupda baş 
verən dəyişiklikləri analiz etməkdir. Nəzərə almaq lazımdır ki, ilk cədvəldə unikal müştəri sayını 
(Distinctcount) hesablamalı, ikinci cədvəldə isə faizi (% Of) istifadə edilməlidir. Analizə baxaraq 
aylar üzrə müştəri sayının dəyişməsi(say və faiz) haqqında informasiya sahibi ola bilirik. 
Məsələn, yanvar ayında kampaniyaya qoşulan müştərilərin 27,46%-i dekabr ayında da alış 
etməyə davam edib. vs. Şərtə əsasən slicer yaradılır və hər iki cədvəllə əlaqə qurulur.  
2.“Stabil” adlı səhifə yaradaraq:  
Kampaniyalardan aylar üzrə əldə olunan gəliri tapın hansı 3 kampaniyanın daha stabil gəlir 
gətidiyini müəyyən edin. Kampaniya adlarına şərti format tətbiq edilməlidir.  
Sabitlik, bir kampaniyanın gəlirlərinin zamanla daha az dəyişməsi ilə bağlıdır. Yəni, gəlirlərdəki 
dəyişkənlik nə qədər azdırsa, kampaniya o qədər sabit sayılır. Stabil gəliri tapmaq üçün Pivot 
Table-dan istifadə edərək aylar üzrə kampaniyalardan əldə olunan gəlir tapılır daha sonra 
standart sapmanı orta gəlirə bölməklə hər kampaniyana üzrə stabillik faizi tapılır(Məs, 
=STDEV.S(B3:M3)/AVERAGE(B3:M3)).  
3.“Pareto” adlı səhifə yaradaraq:   
Kampaniyalardan əldə olunan gəlirə əsasən Pareto analizi edin. 
Pareto analizi, bir problemin və ya hadisənin səbəblərini təhlil edərkən, ən mühüm azsaylı 
səbəblərin (20%) əksəriyyət nəticələrin (80%) məsul olduğunu göstərən prinsipi əsas alan bir 
analiz metodudur. Pareto analizini etmək üçün kumulativ cəm və kumulativ faiz hesablanır. 
Combo və ya Pareto qrafikindən istifadə edilərək diaqram yaradılır. 
