# EMRStudioDemo

This is a demo Spark notebook to use for showing execution of parameterized jupyter notebooks.

Run the notebook in EMR Studio:-
=================================
aws emr --region us-east-1 \
      start-notebook-execution \
      --editor-id e-AFYR76ILE2F9PXRGMZMKXXXX \
      --notebook-params '{"s3file":"yellow_tripdata_2021-04.csv"}' \
      --relative-path miles-per-rate.ipynb \
      --notebook-execution-name my-execution \
      --execution-engine '{"Id" : "j-3T8B043N3XXXX"}' \
      --service-role EMR_Notebooks_DefaultRole
      
Check Status of the job and the S3 location of the output notebook:-
=====================================================================

aws emr --region us-east-1 \
      describe-notebook-execution --notebook-execution-id ex-J00H4QLXPMF28YLIFJK1O66NYMYWO
