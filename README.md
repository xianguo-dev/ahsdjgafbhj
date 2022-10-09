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
python build_rawframes.py /home/xianguo/save/TSNDataSet/TSN视频数据集 /home/xianguo/framesoutput/TSNInput --task flow --level 2 \
    --num-worker 8 --flow-type tvl1 \
    --resume --mixed-ext

python tools/data/build_file_list.py ${DATASET} ${SRC_FOLDER} [--rgb-prefix ${RGB_PREFIX}] \
    [--flow-x-prefix ${FLOW_X_PREFIX}] [--flow-y-prefix ${FLOW_Y_PREFIX}] [--num-split ${NUM_SPLIT}] \
    [--subset ${SUBSET}] [--level ${LEVEL}] [--format ${FORMAT}] [--out-root-path ${OUT_ROOT_PATH}] \
    [--seed ${SEED}] [--shuffle]
    
    python tools/data/build_file_list.py ucf101 /home/xianguo/framesoutput/TSNInput [--rgb-prefix ${RGB_PREFIX}] \
    [--flow-x-prefix ${FLOW_X_PREFIX}] [--flow-y-prefix ${FLOW_Y_PREFIX}] [--num-split ${NUM_SPLIT}] \
    [--subset ${SUBSET}] [--level ${LEVEL}] [--format ${FORMAT}] [--out-root-path ${OUT_ROOT_PATH}] \
    [--seed ${SEED}] [--shuffle]
