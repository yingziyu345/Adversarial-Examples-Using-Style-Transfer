# Adversarial-Examples-Using-Style-Transfer
直接运行code.py即可。

original photos and results.zip中有五个个文件夹：photo中是初始十张图片和两种风格图片；output中是lambda_adv = 10,alpha = 1e5,beta = 1e3(num_steps=400)的生成的对抗样本；output1中是lambda_adv = 10,alpha = 1e7,beta = 1e3(num_steps=400)的生成的对抗样本；output2中是lambda_adv = 10,alpha = 1e7,beta = 1e3（num_steps=300）的生成的对抗样本；output2中是lambda_adv = 10,alpha = 1e5,beta = 10（num_steps=400）。

根据output结果可以看出对抗样本视觉上与原图差别不大，但被机器错误分类为目标类别439(bearskin)；当把风格迁移的参数调大，从output1结果可以明显看出对抗样本图片风格改变（趋向于梵高星空的风格），同时有一张图也被分类错误（图片9被分错不是原类别也不是目标类别）；降低num_steps后，从output2中看到图片8被归类为原类别（优化步骤减少说明生成的对抗样本可能还没有充分调整，导致它可能无法成功欺骗分类器。），图片9被分为其他类别（不是原类别和目标类别）；output3中图片也都被误分类为指定目标，但与output1比图像迁移风格更明显（内容损失权重降低导致更偏向于风格迁移）。
