# Spark UDF 작성 시 Python-JVM 통신비용, DataFrame/Scala 권장 메모
*작성 2019-09-05 · 수정 2019-09-05*

유저 함수 작성시 파이썬 기준인 경우 python - jvm - scalar 간 통신비용이 있어 성능이 좋지 않음  
df는 최적화되어서 파이썬으로 가공해도 문제 없다 함 -> 스칼라로 하는 게 좋다 함
