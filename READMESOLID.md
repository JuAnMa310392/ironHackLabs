# Problema identificado
El código original de la clase SystemManager presenta múltiples responsabilidades, incluyendo el procesamiento de órdenes y la interacción con servicios externos, lo que viola el principio de responsabilidad única (SRP). Además, la clase depende directamente de implementaciones concretas de servicios de pago, violando así el principio de inversión de dependencias (DIP). Por último, el código no está abierto a la extensión, ya que no proporciona una forma fácil de agregar nuevos métodos de procesamiento de pago ni tipos de notificaciones sin modificar la clase SystemManager, lo que viola el principio de abierto/cerrado (OCP)


____________

# Código refactorizado
enum NotificationType { EMAIL, SMS }

´´´yaml
class Order {

private String id;
private String name;
private PaymentType type;
private com.project.ironHack.entites.NotificationType notificationType;
private double amount;
private boolean inStock;
}
´´´
