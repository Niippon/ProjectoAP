# ProjectoAP

#include "stdafx.h"
#include "string.h"
#define true 1

typedef struct Lugar
{
	int numLugar;
	char fila;
};

typedef struct PReserva
{
	int n;
	char nome[40];
	char nifPass[10];
	char sala;
	Lugar lugaresReservados[6];
};

typedef struct CC
{
	int MCC[11][11];
	int numReservas;
	int numBilhetesVendidos;
	int numLugaresLivres;
	float percentBilhetesVendidos;
	float percentLugaresReservados;
	float receitaActual;
	float custoBilhete;
};

typedef struct BB
{
	int  MBB[10][8];
};


PReserva ReservaLer()
{
	PReserva k;
	printf("\nQuantas reservas pretende fazer: ");
	scanf_s("%d",&k.n);
	fflush(stdin);
	printf("\nDigite o Nome: ");
	gets_s(k.nome);
	printf("\nDigite o NIF ou o Passaporte: ");
	gets_s(k.nifPass);
	for(int i=0; i<k.n; i++)
	{
		printf("\nDigite a Fila: ");
		scanf_s("%c",&k.lugaresReservados[i].fila);
		fflush(stdin);
		printf("\nDigite o Numero do Lugar: ");
		scanf_s("%d",&k.lugaresReservados[i].numLugar);
		fflush(stdin);
	}
	return k;
}

void ReservaImprimir(PReserva k)
{
	printf("\n\n\n\nNome: %s",k.nome);
	printf("\n\nNIF ou Passaporte: %s",k.nifPass);
	for(int i=0; i<k.n; i++)
	{
		printf("\n\nLugar Reservado: %c%d",k.lugaresReservados[i].fila,k.lugaresReservados[i].numLugar);
		printf("\n");
	}
}

void main()
{
	int opcao,opReser, opVB, opVBR, opVis;
	PReserva pessoas[5];

	while (true)
	{
		printf("\n===============================================================================");
		printf("\n====================       GESTAO DE SALAS DE CINEMA       ====================");
		printf("\n===============================================================================\n\n");
		printf("\n1 - Para Aceder a Reserva de Bilhetes");
		printf("\n\n2 - Para Aceder a Venda de Bilhetes");
		printf("\n\n3 - Para Aceder a Venda de Bilhetes Reservados");
		printf("\n\n4 - Para Visualizar Salas");
		printf("\n\n5 - Para Sair do Programa");
		printf("\n\nOpcao: ");
		scanf_s("%d",&opcao);
		printf("\n");
		switch(opcao)
		{
			case 1:
				printf("\n===========================   RESERVA DE BILHETES   ============================");
				printf("\n\n1 - Para efectuar Reserva na Sala CC - Charlin Chaplin");
				printf("\n\n2 - Para efectuar Reserva na Sala BB - Brigite Bardot");
				printf("\n\nOpcao: ");
				scanf_s("%d",&opReser);
				if(opReser == 1)
					printf("\nSala CC\n\n");
				else if(opReser == 2)
						printf("\nSala BB\n\n");
					else
						printf("\nOpcao Invalida\n\n");
				/*printf("\n=============================   DADOS DE ENTRADA   =============================");
				for(int z=0; z<5; z++)
				{
					pessoas[z] = ReservaLer();
				}
				printf("\n=====================   DADOS DAS PESSOAS REGISTADAS   =====================");*/
				//ReservaImprimir(pessoas);
				break;
			case 2:
				printf("\n============================   VENDA DE BILHETES   =============================");
				printf("\n\n1 - Para efectuar Venda de Bilhetes para Sala CC - Charlin Chaplin");
				printf("\n\n2 - Para efectuar Venda de Bilhetes para Sala BB - Brigite Bardot");
				printf("\n\nOpcao: ");
				scanf_s("%d",&opVB);
				if(opVB == 1)
					printf("\nSala CC\n\n");
				else if(opVB == 2)
						printf("\nSala BB\n\n");
					else
						printf("\nOpcao Invalida\n\n");
				break;
			case 3:
				printf("\n=======================   VENDA DE BILHETES RESERVADOS   =======================");
				printf("\n\n1 - Para efectuar Venda de Bilhetes Reservados na Sala CC - Charlin Chaplin");
				printf("\n\n2 - Para efectuar Venda de Bilhetes Reservados na Sala BB - Brigite Bardot");
				printf("\n\nOpcao: ");
				scanf_s("%d",&opVBR);
				if(opVBR == 1)
					printf("\nSala CC\n\n");
				else if(opVBR == 2)
						printf("\nSala BB\n\n");
					else
						printf("\nOpcao Invalida\n\n");
				break;
			case 4:
				printf("\n=============================   VISUALIZAR SALAS   =============================");
				printf("\n\n1 - Para visualizar Sala CC - Charlin Chaplin");
				printf("\n\n2 - Para visualizar Sala BB - Brigite Bardot");
				printf("\n\nOpcao: ");
				scanf_s("%d",&opVis);
				if(opVis == 1)
					printf("\nSala CC\n\n");
				else if(opVis == 2)
						printf("\nSala BB\n\n");
					else
						printf("\nOpcao Invalida\n\n");
				break;
			case 5:
				printf("Sair");
				break;
			default: 
				printf("\nOpcao Invalida\n\n");
		}
	}
}

