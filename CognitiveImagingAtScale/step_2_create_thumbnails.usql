REFERENCE ASSEMBLY [Build].[DemoAsm];

@imgs = SELECT * FROM Build.dbo.Megaface;

@thumbs = 
    SELECT 
      FileName, 
      Demo.Helpers.CreateThumbnail( ImgData ) AS ImgData
    FROM @imgs;

DROP TABLE IF EXISTS Build.dbo.MegafaceThumbs;

CREATE TABLE Build.dbo.MegafaceThumbs
( 
    INDEX idx  
    CLUSTERED(FileName ASC)
    DISTRIBUTED BY HASH(FileName) 
) AS SELECT * FROM @thumbs;

