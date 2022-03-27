Клеточная линия: HepG2

Список гистоновых меток:

H2az	Hepg2H2azStdAlnRep1.bam	

H3k04me1	Hepg2H3k04me1StdAlnRep1.bam	

H3k09me3	Hepg2H3k09me3AlnRep1.bam	

H3k4me2	Hepg2H3k4me2StdAlnRep1.bam	

H3k9ac	Hepg2H3k9acStdAlnRep1.bam	

H3k27ac	Hepg2H3k27acStdAlnRep1.bam	

H3k27me3	Hepg2H3k27me3StdAlnRep1.bam	

H3k36me3	Hepg2H3k36me3StdAlnRep1.bam	

H3k79me2	Hepg2H3k79me2StdAlnRep1.bam	

H4k20me1	Hepg2H4k20me1StdAlnRep1.bam	


Контроль: Hepg2ControlStdAlnRep1.bam

Рисунки из выдачи ChromHMM:

![emissions_10](https://user-images.githubusercontent.com/72361668/160193174-bf8213b7-0dbe-4c23-aa1e-98f71eff9893.png)
![Hepg2_10_overlap](https://user-images.githubusercontent.com/72361668/160193191-907856b5-16a9-406e-a7d7-243afa6cd491.png)
![Hepg2_10_RefSeqTES_neighborhood](https://user-images.githubusercontent.com/72361668/160193198-e18c5ac8-f6e4-4550-a584-0c14db3513ef.png)
![Hepg2_10_RefSeqTSS_neighborhood](https://user-images.githubusercontent.com/72361668/160193204-1edaf769-1a3e-4b9f-bf64-b1a9205b30d3.png)
![transitions_10](https://user-images.githubusercontent.com/72361668/160193219-e78353f8-f78b-4e9e-adae-697140e9c365.png)


Классификация состояний:


1 (промотор 2) вместе с 2 покрывает практически все cpg островки. На это состояние приходятся пики экспрессии гистоновых меток (см рис). 

2 (промотор 1) перекрывает cpg островки, скорее всего находится в промоторах. Большая часть cpg островков приходится на это состояние. Часто приходится на сайт начала транскрипции (TSS) (см рис fold enrichment).

3 и 4 часто идут поочередно, приходятся на пики экспрессии гистоновых меток.

4 соответствует преимущественно одной метке - h3k4me1.

5 (гены 2) и 6 приходятся на интроны.

6 (гены 1) встречается практически только в аннотированных генах (см рис fold enrichment).

7 - часто встречается относительно длинными кусками, иногда чередуясь с 9. Соответствует генам (включая сайты конца транскрипции).

8 (гетерохроматин) соответствует единственной метке, которая не присутствует в других состояниях: h3k9me3. Соответствует доменам, ассоциированным с ядерной ламией (гетерохроматин) (см fold enrichment).

9 (без гистоновых меток) - самое частое состояние (см рис fold enrichment), большие отрезки. Это соостояние соответствует отсутствию гистоновых меток (см рис emission parameters).
Изредка приходится на cpg островки.

10 соответствует яркому выражению метки h3k27me3 и более слабому проявлению метки h4k20me1 (см рис emission parameters).


Список команд:

Установака:

!curl -O https://raw.githubusercontent.com/deepjavalibrary/d2l-java/master/tools/fix-colab-gpu.sh && bash fix-colab-gpu.sh

!curl -O https://raw.githubusercontent.com/deepjavalibrary/d2l-java/master/tools/colab_build.sh && bash colab_build.sh

!java --list-modules | grep "jdk.jshell"

! wget http://compbio.mit.edu/ChromHMM/ChromHMM.zip

!unzip /content/ChromHMM.zip

Скачивание файлов:

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H2azStdAlnRep1.bam -O Hepg2H2azStdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k04me1StdAlnRep1.bam -O Hepg2H3k04me1StdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k09me3AlnRep1.bam -O Hepg2H3k09me3AlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k4me2StdAlnRep1.bam -O Hepg2H3k4me2StdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k9acStdAlnRep1.bam -O Hepg2H3k9acStdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k27acStdAlnRep1.bam -O Hepg2H3k27acStdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k27me3StdAlnRep1.bam -O Hepg2H3k27me3StdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k36me3StdAlnRep1.bam -O Hepg2H3k36me3StdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H3k79me2StdAlnRep1.bam -O Hepg2H3k79me2StdAlnRep1.bam

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2H4k20me1StdAlnRep1.bam -O Hepg2H4k20me1StdAlnRep1.bam

#control

!wget http://hgdownload.cse.ucsc.edu/goldenPath/hg19/encodeDCC/wgEncodeBroadHistone/wgEncodeBroadHistoneHepg2ControlStdAlnRep1.bam -O Hepg2ControlStdAlnRep1.bam

ChromHMM:

!java -mx5000M -jar /content/ChromHMM/ChromHMM.jar BinarizeBam -b 200  /content/ChromHMM/CHROMSIZES/hg19.txt /content/ cellmarkfiletable.txt   binarizedData

from google.colab import drive

drive.mount('/content/drive')

!java -mx5000M -jar /content/ChromHMM/ChromHMM.jar LearnModel  -b 200 binarizedData /content/drive/MyDrive/hw_HMM 10 hg19


Бонус:

fin = open("/content/drive/MyDrive/hw_HMM/Hepg2_10_expanded.bed")

fout = open("/content/drive/MyDrive/hw_HMM/Hepg2_10_edited_expanded.bed", 'w')

for line in fin:

  a = line.split()
  
  if len(a) < 4:
  
    print('\t'.join(a), file=fout)
    
    continue
    
  if a[3] == '1':
  
    a[3] = 'Promoter_2'
    
  if a[3] == '2':
  
    a[3] = 'Promoter_1_TSS'
    
  if a[3] == '3':
  
    a[3] = '3'
    
  if a[3] == '4':
  
    a[3] = 'h3k4me1'
    
  if a[3] == '5':
  
    a[3] = 'Gene_2'
    
  if a[3] == '6':
  
    a[3] = 'Gene_1'
    
  if a[3] == '7':
  
    a[3] = 'Gene_3_TES'
    
  if a[3] == '8':
  
    a[3] = 'Heterochromatin'
    
  if a[3] == '9':
  
    a[3] = 'no_histone_mark'
    
  if a[3] == '10':
  
    a[3] = 'h3k27me3'
    
  print('\t'.join(a), file=fout)
  
fout.close()

fin.close()

<img width="966" alt="expanded_edited" src="https://user-images.githubusercontent.com/72361668/160298737-33a19054-4d33-404e-98b3-96463c39c364.png">
<img width="827" alt="dense_edited" src="https://user-images.githubusercontent.com/72361668/160298738-bac1fcfc-15db-42b8-a53f-cec85dc9183a.png">
