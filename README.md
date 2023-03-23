# Verdict NLP applications

## Installation
```
pip install paddlepaddle
pip install --upgrade paddlenlp
python3 -m  pip install scikit-learn==1.0.2
```

## Text classfication
### Finetune
```
cd textclassfication/finetune
python train.py \                                                     
--dataset_dir "data/dataset" \
--device "cpu" \
--max_seq_length 128 \
--model_name "ernie-3.0-medium-zh" \
--batch_size 32 \
--early_stop \
--epochs 10
```
### Few-shot prompt learning
```
cd textclassfication/few-shot
python train.py \
--data_dir ./data/ \
--device "cpu" \
--output_dir ./checkpoints/ \
--prompt "這句話要包含的要素有" \
--model_name_or_path ernie-3.0-base-zh \
--max_seq_length 128  \
--learning_rate 3e-5 \
--ppt_learning_rate 3e-4 \
--do_train \
--do_eval \
--do_predict \
--do_export \
--num_train_epochs 10 \
--logging_steps 5 \
--save_total_limit 1 \
--per_device_eval_batch_size 32 \
--per_device_train_batch_size 8 \
--metric_for_best_model macro_f1_score \
--load_best_model_at_end \
--evaluation_strategy epoch \
--save_strategy epoch
```

