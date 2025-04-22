# Proyecto Integrador 4° Semestre Grupo B

## **Datos del Equipo**  
**Institución**: Instituto Tecnológico Superior del Occidente del Estado de Hidalgo.  
**Programa Educativo**: Ingeniería en Tecnologías de la Información y Comunicaciones.  
**Semestre y Grupo**: 4° "B".  
**Asignatura**: Fundamentos de Redes.  

**Integrantes**:    
- Abraham Calva (230110637)  
- Freyra Wendy Martinez Martinez (230110434)  
- Karol Mera Ibarra (230110264)
- Valeria Soto Hernandez (230110118)   
---
## **Problematica:**


La gestión de pedidos en la florería se realiza de manera manual o con métodos poco organizados, lo que genera dificultades en el control de los pedidos, retrasos en las entregas y posibles errores en la administración de clientes, productos y pagos. Esto impacta negativamente en la eficiencia operativa del negocio y en la satisfacción del cliente, ya que no se cuenta con un sistema que permita organizar y automatizar los procesos de forma eficiente.
---
## **Objetivo General**

Desarrollar un sistema informático que permita la gestión eficiente de la agenda de pedidos de una florería, clientes, productos y envíos a domicilio,  mediante una bases de datos, un lenguaje de programación; implementado en una red de comuputadora cliente servidor.

---

## **Alcance Técnico de la Topología**  
1. **Asignación de Direcciones IP:**

- Se utilizará un bloque IPv4 privado clase C (172.16.0.0/24), dividido en subredes para organizar de forma eficiente el direccionamiento.


2. **Soporte para IPv6:**

- Se integrará direccionamiento Global Unicast (2001:db8::/64) junto con Link-Local automático, permitiendo conectividad moderna y facilitando la futura migración completa a IPv6.

3. **Parámetros de Configuración:**

- Router: Se habilitará el enrutamiento IPv6, se establecerán contraseñas cifradas tipo Secret y se activará el acceso remoto vía SSH.

- Switch: Se configurará la interfaz VLAN1 con dirección IPv4, gateway predeterminado y una descripción administrativa.

---
## **Cálculo de  Subred en Equipo 4**  
**Dirección IP:** 172.16.0.0 /24  
**Máscara:** 255.255.255.0  
**Número de Subredes:** 8    
**Nueva máscara:** 255.255.255.224  =  /27   

<table>
    <tr>
        <td> <strong>172.16.0.</strong> </td>
        <td> <strong>128</strong> </td>
        <td> <strong>64</strong> </td>
        <td> <strong>32</strong> </td>
        <td> <strong>16</strong> </td>
        <td> <strong>8</strong> </td>
        <td> <strong>4</strong> </td>
        <td> <strong>2</strong> </td>
        <td> <strong>1</strong> </td>
        <td> 
            <strong>Network ID</strong>
            <p style="text-align: center">
            <strong>Broadcast</strong>
            </td>
            <td><strong>1er Dirección</strong>
            <p style="text-align: center">
            <strong>Ult. Dirección</strong>
        </td>
    </tr>
    <tr>
        <td rowspan="2" > <strong>Equipo 1</strong> </td>
        <td>0 </td>
        <td>0 </td>
        <td>0 </td>
        <td> </td>
        <td> </td>
        <td> </td>
        <td> </td>
        <td> </td>
        <td> </td>
        <td> </td>
    </tr>
    <tr>
        <td> 0 </td>
        <td> 0 </td>
        <td> 0 </td>
        <td> </td>
        <td> </td>
        <td> </td>
        <td> </td>
        <td> </td>
        <td> </td>
        <td> </td>
    </tr>
    <tr>
        <td rowspan="2" ><strong>Equipo 2</strong></td>
        <td>0</td>
        <td>0</td>
        <td>1</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>0</td>
        <td>0</td>
        <td>1</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td rowspan="2" ><strong>Equipo 3</strong></td>
        <td>0</td>
        <td>1</td>
        <td>0</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>0</td>
        <td>1</td>
        <td>0</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td rowspan="2" ><strong>Equipo 4</strong></td>
        <td>0</td>
        <td>1</td>
        <td>1</td>
        <td>0</td>
        <td>0</td>
        <td>0</td>
        <td>0</td>
        <td>0</td>
        <td>172.16.0.96</td>
        <td>172.16.0.97</td>
    </tr>
    <tr>
        <td>0</td>
        <td>1</td>
        <td>1</td>
        <td>1</td>
        <td>1</td>
        <td>1</td>
        <td>1</td>
        <td>1</td>
        <td>172.16.0.127</td>
        <td>172.16.0.126</td>
    </tr>
</table>

--- 

## **Direccionamiento de nuestra subred**
<table>
    <tr>
        <td colspan="5" ><strong>Switch SD</strong> </td>
    </tr>
    <tr>
        <td> <strong>Interface</strong> </td>
        <td> <strong>IPv4</strong> </td>
        <td> <strong>Máscara</strong> </td>
        <td> <strong>IPv6 Link-Local</strong> </td>
        <td> <strong>IPv6 Global (eui-64)</strong> </td>
    </tr>
    <tr>
        <td> VLAN 1 </td>
        <td> 172.16.0.97 </td>
        <td> 255.255.255.224 </td>
        <td> FE80::1 </td>
        <td> 2001:db8:1:d::/64</td>
    </tr>
</table>
<table>
    <tr>
        <td colspan="5" > <strong>Router RD</strong> </td>
    </tr>
    <tr>
        <td> <strong>Interface</strong> </td>
        <td> <strong>IPv4</strong> </td>
        <td> <strong>Máscara</strong> </td>
        <td> <strong>IPv6 Link-Local</strong> </td>
        <td> <strong>IPv6 Global (eui-64)</strong> </td>
    </tr>
    <tr>
        <td> GigabitEthernet 0/1 </td>
        <td> 172.16.0.98 </td>
        <td> 255.255.255.224 </td>
        <td> FE80::1 </td>
        <td> 2001:db8:1:d::/64 </td>
    </tr>
</table>





--- 

## **Topología**
<img src="img/topologia.jpg" height="500px" />    
La topología utilizada en este proyecto es la que se muestra en pantalla y que tambien puedes encontrar en: <a href="conexiones ipv4-ipv6.pkt">Conexiones ipv4-ipv6.pkt</a>  

---
## **Configuraciones de los equipos (Switch y Router)**
### **Switch RD**
1. **Asignar nombre del host**
2. **Configurar Banner**
3. **Configurar contraseñas:**
   - Contraseña no cifrada  y cifrada 
   - Contraseña de la consola
   - Cifrar todas las contraseñas
4. **Configurar acceso remoto:**
   - Telnet
   - SSH
5. **Activar el uso de IPv4 e IPv6**
6. **Configuración de la interface Vlan1**
   - Asignar IPv4 y máscara de subred
   - Asignar el default gateway
   - Asignar dirección Global IPv6
   - Asignar dirección link-local IPv6
   - Agregar una descripción

<details> 
    <summary>
       Resumen de las configuraciones hechas en el Switch SD
    </summary>
    <pre>
    ## AGREGA AQUI LAS CONFIGURACIONES AMOR, PUEDEN SER EN IMAGENES O COMO CODIGO
    </pre>
</details>

### **Router RD**
1. **Asignar nombre del host**
2. **Configurar Banner**
3. **Configurar contraseñas:**
   - Contraseña no cifrada  y cifrada
   - Contraseña de la consola
   - Cifrar todas las contraseñas
4. **Configurar acceso remoto:**
   - Telnet
   - SSH
5. **Activar el enrutamiento IPv6**
6. **Configuración de la interface GigabitEthernet:**
   - Asignar IPv4 y máscara de subred
   - Asignar dirección Global IPv6
   - Asignar dirección link-local IPv6
   - Agregar una descripción

<details> 
    <summary>
        Resumen de las configuraciones hechas en el Switch SD
    </summary>
    <pre>
   ## AGREGA AQUI LAS CONFIGURACIONES AMOR, PUEDEN SER EN IMAGENES O COMO CODIGO
    </pre>
</details>

