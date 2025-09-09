#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main() {
	int many, in[100], out[100], id, a[100];
	int hap1=0, hap2=0, max = 0, min = 10;
	float per=0;
	printf("개수 : ");
	scanf("%d", &many);
	printf("입고 수량 : ");
	for (int i = 0;i < many;i++) {
		scanf("%d", &in[i]);
	}
	printf("판매 수량 : ");
	for (int i = 0;i < many;i++) {
		scanf("%d", &out[i]);
	}
	for (int i = 0;i < many;i++) {
		a[i] = in[i] - out[i];
	}
	printf("ID : ");
	scanf("%d", &id);
	printf("%d\n", a[id - 1]);

	printf("재고 수량 : ");
	for (int i = 0;i < many;i++) {
		printf("%d ", a[i]);
	}
	for (int i = 0;i < many;i++) {
		hap2 = hap2 + out[i];
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
