训练ＴＳＮ：
python main.py ucf101 RGB ucf101_rgb_train_list.txt ucf101_rgb_val_list.txt     --arch BNInception --num_segments 3 \   --gd 20 --lr 0.001 --lr_steps 30 60 --epochs 80 \    -b 128 -j 8 --dropout 0.8 \    --snapshot_pref ucf101_bninception_ 

python main.py ucf101 RGB /home/xianguo/mmaction2-master/data/ucf101/ucf101_train_split_1_rawframes.txt /home/xianguo/mmaction2-master/data/ucf101/ucf101_val_split_1_rawframes.txt \
   --arch BNInception --num_segments 15 \
   --gd 20 --lr 0.001 --lr_steps 30 60 --epochs 80 \
   -b 128 -j 8 --dropout 0.8 \
   --snapshot_pref ucf101_bninception_ 
   
   python main.py ucf101 Flow /home/xianguo/mmaction2-master/data/ucf101/ucf101_train_flow_split_1_rawframes.txt /home/xianguo/mmaction2-master/data/ucf101/ucf101_val_flow_split_1_rawframes.txt \
   --arch BNInception --num_segments 3 \
   --gd 20 --lr 0.001 --lr_steps 190 300 --epochs 340 \
   -b 128 -j 4 --dropout 0.7 \
   --snapshot_pref ucf101_bninception_ --flow_pref flow_  
   
   python main.py ucf101 RGB /home/xianguo//tsn-pytorch/ucf101_rgb_train_list.txt  /home/xianguo//tsn-pytorch/ucf101_rgb_val_list.txt    --arch BNInception --num_segments 3    --gd 20 --lr 0.001 --lr_steps 30 60 --epochs 80    -b 128 -j 8 --dropout 0.8    --snapshot_pref ucf101_bninception_ 

测试ＴＳＮ
python test_models.py ucf101 RGB /home/xianguo/mmaction2-master/data/ucf101/ucf101_val_split_1_rawframes.txt ucf101_bninception__rgb_checkpoint.pth.tar \
   --arch BNInception --save_scores 5ActionTestScore_RGB

提取帧
python build_rawframes.py ${SRC_FOLDER} ${OUT_FOLDER} [--task ${TASK}] [--level ${LEVEL}] \
    [--num-worker ${NUM_WORKER}] [--flow-type ${FLOW_TYPE}] [--out-format ${OUT_FORMAT}] \
    [--ext ${EXT}] [--new-width ${NEW_WIDTH}] [--new-height ${NEW_HEIGHT}] [--new-short ${NEW_SHORT}] \
    [--resume] [--use-opencv] [--mixed-ext]
CUDA_VISIBLE_DEVICES=1 python build_rawframes.py /home/xianguo/save/BMNDataset1 /home/xianguo/framesoutput/BMNDataset --task flow --level 1 \
    --num-worker 1 --flow-type tvl1  \
 --mixed-ext

python tools/data/build_file_list.py ${DATASET} ${SRC_FOLDER} [--rgb-prefix ${RGB_PREFIX}] \
    [--flow-x-prefix ${FLOW_X_PREFIX}] [--flow-y-prefix ${FLOW_Y_PREFIX}] [--num-split ${NUM_SPLIT}] \
    [--subset ${SUBSET}] [--level ${LEVEL}] [--format ${FORMAT}] [--out-root-path ${OUT_ROOT_PATH}] \
    [--seed ${SEED}] [--shuffle]
    
    python tools/data/build_file_list.py ucf101 /home/xianguo/framesoutput/TSNInput/outdoor/  --level 1 --format rawframes --out-root-path /home/xianguo/mmaction2-master/data/ 
      python tools/data/build_file_list.py ucf101 /home/xianguo/framesoutput/TSNInput/  --level 2 --format rawframes --out-root-path /home/xianguo/mmaction2-master/data/ --RgbOrFlow flow
