#include <stdio.h>
#include <string.h>

int main() {
    char nombre[50];
    char contrasena[50];
    int intentos = 3;
    int cantidad;
    float precioUnitario;
    float importeTotal = 0;

   
    do {
        printf("Introduce tu nombre: ");
        scanf("%s", nombre);

        printf("Introduce tu contraseña: ");
        scanf("%s", contrasena);

        if (strcmp(nombre, "osvaldo") == 0 && strcmp(contrasena, "2B21") == 0) {
            printf("Bienvenido al sistema.\n");
            break;
        } else {
            intentos--;
            if (intentos > 0) {
                printf("Nombre de usuario o contraseña incorrectos. Te quedan %d intentos.\n", intentos);
            } else {
                printf("Se ha superado el número de intentos permitido.\n");
                return 1; 
            }
        }
    } while (intentos > 0);

  
    printf("\nAhora vamos a calcular el importe de la factura.\n");
    printf("Por favor introduce la cantidad y el precio unitario de cada artículo.\n");
    printf("Cuando hayas terminado, introduce 0 en la cantidad para finalizar.\n\n");

   
    printf("Cantidad: ");
    scanf("%d", &cantidad);
    while (cantidad != 0) {
        printf("Precio unitario: ");
        scanf("%f", &precioUnitario);

        if (cantidad < 0 || precioUnitario < 0) {
            printf("Error: la cantidad y el precio deben ser números positivos.\n\n");
        } else {
            float importe = cantidad * precioUnitario;
            importeTotal += importe;
        }

        printf("\nCantidad: ");
        scanf("%d", &cantidad);
    }
    
    printf("\nImporte total de la factura: %.2f\n", importeTotal);

    return 0;
}
