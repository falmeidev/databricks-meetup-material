## Reading the files

```sql

WITH 

calc_pontos AS (
  SELECT
      YEAR(data) AS ano,
      mandante AS time,
      SUM(CASE 
              WHEN vencedor = mandante THEN 3
              WHEN vencedor = '-' THEN 1
              ELSE 0
          END) AS pontos
  FROM
      bronze.brasileirao.campeonato_brasileiro_full
  GROUP BY
      ano, mandante

  UNION ALL

  SELECT
      YEAR(data) AS ano,
      visitante AS time,
      SUM(CASE 
              WHEN vencedor = visitante THEN 3
              WHEN vencedor = '-' THEN 1
              ELSE 0
          END) AS pontos
  FROM
      bronze.brasileirao.campeonato_brasileiro_full
  GROUP BY
      ano, visitante
  ORDER BY
      ano, time
)

SELECT 
  ano,
  time,
  SUM(pontos)
FROM calc_pontos
GROUP BY 1,2
```

```sql
SELECT 
jogos.*,
gols.atleta,
gols.minuto 
FROM bronze.brasileirao.campeonato_brasileiro_full jogos
LEFT JOIN bronze.brasileirao.campeonato_brasileiro_gols gols ON gols.partida_id = jogos.ID
WHERE mandante LIKE "%Botafogo%" AND DATE_TRUNC('YEAR', data) = '2023' AND jogos.rodata = 31 
ORDER BY minuto ASC
```



