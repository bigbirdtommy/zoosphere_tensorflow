# zoosphere_tensorflow
Tensorflow custom trained inception model using the datasets from ZooSphere 

All datasets extracted from ZooSphere
http://www.zoosphere.net/

Trained via the "Tensorflow for Poets" walkthrough on TF 1.3
https://petewarden.com/2016/02/28/tensorflow-for-poets/


training

 bazel-bin/tensorflow/examples/image_retraining/retrain --bottleneck_dir=/zoosphere/labelgen/bottlenecks/ --model_dir=/zoosphere/labelgen/inception --output_graph=/zoosphere/labelgen/output/zs_retrained_graph.pb --output_labels=/zoosphere/labelgen/output/zs_retrained_labels.txt --image_dir=/zoosphere/labelgen/sourceimages/

labeling

 bazel-bin/tensorflow/examples/label_image/label_image --graph=/zoosphere/labelgen/output/zs_retrained_graph.pb --labels=/zoosphere/labelgen/output/zs_retrained_labels.txt --output_layer=final_result --input_layer=Mul --image=
 
