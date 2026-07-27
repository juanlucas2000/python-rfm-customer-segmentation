RFM Customer Segmentation — Online Retail II

Segmentación de clientes usando la metodología RFM (Recencia, Frecuencia, Monetario) sobre el dataset de Online Retail II, reutilizando los datos ya limpiados en el proyecto de EDA. 

Objetivo: identificar grupos de clientes con comportamientos distintos para priorizar acciones de retención y reactivación.

Dataset
Fuente: datos ya limpios del proyecto python-online-retail-eda (online_retail_clean.csv)
Se analizaron únicamente los 5,878 clientes con Customer ID identificado (se excluyeron las transacciones sin cliente registrado, ~23% del total original)
Metodología
Por cada cliente se calculó:
Recencia: días desde su última compra hasta el día siguiente a la última fecha registrada en el dataset
Frecuencia: número de pedidos (facturas) distintos
Monetario: suma total gastada
Cada métrica se convirtió en un puntaje de 1 a 4 usando cuartiles (qcut), para que la segmentación sea robusta ante valores atípicos
Los 3 puntajes se sumaron en un RFM_Score (rango 3-12), agrupado en 4 segmentos de negocio

Resultados

Cantidad de clientes por segmento RFM
<img width="790" height="490" alt="image" src="https://github.com/user-attachments/assets/5ebd5291-a239-4837-bb07-e8b2bc2d9aaa" />

Frecuencia vs Monetario por segmento
<img width="889" height="590" alt="image" src="https://github.com/user-attachments/assets/d0fc4094-867f-4106-8b04-197d2dc9923c" />

Recencia vs Monetario por segmento 
<img width="889" height="590" alt="image" src="https://github.com/user-attachments/assets/2fd2c54d-1a54-4c26-8cbd-51f81aa5ff5e" />


Dato interesante: el cliente con mayor gasto histórico (£580,987, con 398 pedidos) es un valor atípico frente a la mediana de £868 — casi con certeza un cliente mayorista/B2B, consistente con el perfil de negocio ya identificado en el EDA general.

Herramientas
Python (pandas, matplotlib)
