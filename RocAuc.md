Roc (Receiver Operator Characteristic) - Это двумерный график, состоящий из оси y True Positive Rate (Sensitivity):$$
\frac{TP}{TP + FN}
$$
И оси x False Positive Rate (1- specificity):
$$
	\frac{FP}{FP + TN}
$$
Граф строится путем смещения порога от 0 к 1 при предсказании классов.
Когда в данных классы несбалансированы, то вместо FPR используют precision, которая не реагирует на TN

Auc (Area Under the Curve) - площадь под roc графиком. чем больше площадь, тем точнее модель.
