# 378391-Patrones
-- 1. Distribución total y porcentual de establecimientos por municipio en BC
SELECT 
    municipio,
    COUNT(*) AS total_negocios,
    ROUND(COUNT(*) * 100.0 / SUM(COUNT(*)) OVER(), 2) AS porcentaje_bc
FROM public.denue_inegi_oficial
WHERE cve_ent = 2
GROUP BY municipio
ORDER BY total_negocios DESC;
