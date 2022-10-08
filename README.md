python main.py ucf101 RGB ucf101_rgb_train_list.txt ucf101_rgb_val_list.txt     --arch BNInception --num_segments 3 \   --gd 20 --lr 0.001 --lr_steps 30 60 --epochs 80 \    -b 128 -j 8 --dropout 0.8 \    --snapshot_pref ucf101_bninception_ 

python main.py ucf101 RGB ucf101_rgb_train_list.txt ucf101_rgb_val_list.txt \
   --arch BNInception --num_segments 3 \
   --gd 20 --lr 0.001 --lr_steps 30 60 --epochs 80 \
   -b 128 -j 8 --dropout 0.8 \
   --snapshot_pref ucf101_bninception_ 
   
   python main.py ucf101 RGB /home/xianguo//tsn-pytorch/ucf101_rgb_train_list.txt  /home/xianguo//tsn-pytorch/ucf101_rgb_val_list.txt    --arch BNInception --num_segments 3    --gd 20 --lr 0.001 --lr_steps 30 60 --epochs 80    -b 128 -j 8 --dropout 0.8    --snapshot_pref ucf101_bninception_ 

