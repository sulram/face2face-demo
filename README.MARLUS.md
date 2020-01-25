#TRAIN

python pix2pix.py \
--mode train \
--output_dir photos/output \
--max_epochs 400 \
--input_dir photos/combined \
--which_direction AtoB

#TEST

python pix2pix.py \
--mode test \
--output_dir photos/output_test \
--input_dir photos/combined/val \
--checkpoint photos/output


