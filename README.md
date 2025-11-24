# Tarea4-An-lisis-de-tendencias-virales-y-participaci-n-en-redes-sociales
## Consultas básicas
## Inserción
{
  "Post_ID": "Post_6000",
  "Post_Date": { "$date": "2023-05-10T00:00:00Z" },
  "Platform": "YouTube",
  "Hashtag": "#Comedy",
  "Content_Type": "Short",
  "Region": "USA",
  "Views": 950000,
  "Likes": 120000,
  "Shares": 15000,
  "Comments": 4800,
  "Engagement_Level": "Medium"
}
## Selección 

db.posts.find({ Post_ID: "Post_6000" })


{ "Platform": "TikTok" }

## Actualización  
  { Post_ID: "Post_6000" },  // filtro
  {
    $set: {
      Engagement_Level: "High",
      Views: 1000000,
      Post_Date: ISODate("2023-05-10T00:00:00Z") // si quieres actualizar la fecha
    }
  }
)
## Eliminación de Documentos

{ "Post_ID": "Post_6000" }

## Consultas con filtros y operadores

{ "Platform": "TikTok" }


{ "Views": { "$gt": 4900000 } }


{ "Likes": { "$lt": 50000 } }


 {  Platform: "YouTube",
       Region: "USA",
       likes: { $gt: 100000 }}


{
  "Post_Date": {
    "$gte": { "$date": "2023-05-01T00:00:00Z" },
    "$lte": { "$date": "2023-05-31T00:00:00Z" }
  }
}


{
  "Hashtag": { "$regex": "Challenge", "$options": "i" }
}

## Consultas de agregación para calcular estadísticas (contar, sumar, promediar, etc.).
### Contar
{
      _id: "$Platform",
      total_posts: { $sum: 1 }
    }

### Sumar 
 {
      _id: "$Content_Type",
      total_views: { $sum: "$Views" }
 }
  
### Promedio
{
      _id: "$Platform",
      avg_likes: { $avg: "$Likes" }
    }
