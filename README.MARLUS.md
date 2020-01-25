### anaconda

criei um arquivo `environment-marlus.yml` com tudo que precisei modificar do projeto original.  
funcionou no MAC OS e no UBUNTU

depois de instalar o ambiente, pode ativalo

```
conda activate face2face
```

### frozen models

necessário fazer o download do modelo enviado e os landmarks de face-recognition `shape_predictor_68_face_landmarks.dat`


### rodar experimento

é possivel rodar o experimento pelo arquivo `run_webcam.sh`, ele roda o script python com os argumentos:

```
python run_webcam.py --source 0 --show 1 --landmark-model shape_predictor_68_face_landmarks.dat --tf-model frozen_model_bozo.pb
```

- `source` define o index da webcam (integrada ou externa)
- `show` mostra a captura de video ou os landmarks



### treinar pix2pix-tensorflow (1.4.1)

```
python pix2pix.py \
--mode train \
--output_dir photos/output \
--max_epochs 400 \
--input_dir photos/combined \
--which_direction AtoB
```

### testar

```
python pix2pix.py \
--mode test \
--output_dir photos/output_test \
--input_dir photos/combined/val \
--checkpoint photos/output
```

