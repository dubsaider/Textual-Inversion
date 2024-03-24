# Textual-Inversion

## Model
<https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0>

### Install 
```
git clone https://github.com/huggingface/diffusers
cd diffusers
pip install .
cd examples/textual_inversion
pip install -r requirements.txt
```

### Use
```
export MODEL_NAME="stabilityai/stable-diffusion-xl-base-1.0"
export DATA_DIR="./flowers"

accelerate launch textual_inversion_sdxl.py \
 --pretrained_model_name_or_path=$MODEL_NAME \
--train_data_dir=$DATA_DIR \
 --learnable_property="object" \
 --placeholder_token="<flowers>" \
 --initializer_token="flower" \
 --mixed_precision="fp16" \
 --resolution=512 \
 --train_batch_size=1 \
 --gradient_accumulation_steps=4 \
 --max_train_steps=500 \
 --learning_rate=5.0e-04 \
 --scale_lr \
 --lr_scheduler="constant" \
 --lr_warmup_steps=0 \
 --save_as_full_pipeline \
 --output_dir="./textual_inversion_flower_sdxl"
```

# Examples

soon

