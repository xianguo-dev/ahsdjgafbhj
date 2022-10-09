python main.py ucf101 RGB ucf101_rgb_train_list.txt ucf101_rgb_val_list.txt     --arch BNInception --num_segments 3 \   --gd 20 --lr 0.001 --lr_steps 30 60 --epochs 80 \    -b 128 -j 8 --dropout 0.8 \    --snapshot_pref ucf101_bninception_ 

python main.py ucf101 RGB ucf101_rgb_train_list.txt ucf101_rgb_val_list.txt \
   --arch BNInception --num_segments 3 \
   --gd 20 --lr 0.001 --lr_steps 30 60 --epochs 80 \
   -b 128 -j 8 --dropout 0.8 \
   --snapshot_pref ucf101_bninception_ 
   
   python main.py ucf101 RGB /home/xianguo//tsn-pytorch/ucf101_rgb_train_list.txt  /home/xianguo//tsn-pytorch/ucf101_rgb_val_list.txt    --arch BNInception --num_segments 3    --gd 20 --lr 0.001 --lr_steps 30 60 --epochs 80    -b 128 -j 8 --dropout 0.8    --snapshot_pref ucf101_bninception_ 
python build_rawframes.py ${SRC_FOLDER} ${OUT_FOLDER} [--task ${TASK}] [--level ${LEVEL}] \
    [--num-worker ${NUM_WORKER}] [--flow-type ${FLOW_TYPE}] [--out-format ${OUT_FORMAT}] \
    [--ext ${EXT}] [--new-width ${NEW_WIDTH}] [--new-height ${NEW_HEIGHT}] [--new-short ${NEW_SHORT}] \
    [--resume] [--use-opencv] [--mixed-ext]
