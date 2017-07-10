CREATE DATABASE IF NOT EXISTS Build;

@imgs = 
    EXTRACT 
        FileName string, 
        ImgData byte[]
    FROM @"adl://adltrainingsampledata.azuredatalakestore.net/MegaFace/MegaFace.tsv"
    USING  Extractors.Tsv();

DROP TABLE IF EXISTS Build.dbo.Megaface;

CREATE TABLE Build.dbo.Megaface
( 
    INDEX idx  
    CLUSTERED(FileName ASC)
    DISTRIBUTED BY HASH(FileName) 
) AS SELECT * FROM @imgs;

