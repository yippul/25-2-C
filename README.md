		hap1 = hap1 + in[i];
	}
	printf("\n");
	per = hap1 / hap2;
	printf("총 판매량 : %d (판매율 %.2f)\n", hap2, per);
	for (int i = 0;i < many;i++) {
		if (out[i] > max) {
			max = out[i];
			id = i + 1;
		}
	}
	printf("가장 많이 판매된 상품 : ID %d, 판매량 %d\n", id, max);
	for (int i = 0;i < many;i++) {
		if (out[i] < min) {
			min = out[i];
			id = i + 1;
		}
	}
	printf("가장 적게 판매된 상품 : ID %d, 판매량 %d\n", id, min);

	for (int i = 0;i < many;i++) {
		if (a[i] <= 2) {
			printf("상품 ID %d : 재고부족(%d)\n", i+1, a[i+1]);
		}
	}
	return 0;
}
