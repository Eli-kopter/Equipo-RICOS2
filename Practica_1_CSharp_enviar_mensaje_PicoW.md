# 3.3 Práctica 1 CSharp enviar mensaje a Pico W

```
using System;
using System.Windows.Forms;
using System.IO.Ports;

namespace Interfaz_Practica_1
{
    public partial class Form1 : Form
    {
        SerialPort puertoSerial;

        public Form1()
        {
            InitializeComponent();
            // Suscribirse al evento Load del formulario para cargar los puertos seriales disponibles
            Load += Form1_Load;
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Inicializar ComboBox con los puertos seriales disponibles
            string[] puertosDisponibles = SerialPort.GetPortNames();
            comboBoxPuertos.Items.AddRange(puertosDisponibles);
            if (puertosDisponibles.Length > 0)
            {
                comboBoxPuertos.SelectedIndex = 0; // Seleccionar el primer puerto por defecto
            }
            else
            {
                MessageBox.Show("No se encontraron puertos seriales disponibles.", "Error", MessageBoxButtons.OK, MessageBoxIcon.Error);
            }
        }

        private void btnConectar_Click(object sender, EventArgs e)
        {
            try
            {
                // Configurar el puerto serial
                puertoSerial = new SerialPort(comboBoxPuertos.SelectedItem.ToString(), 9600);
                puertoSerial.Open();
                MessageBox.Show("Conexión establecida correctamente.", "Conexión Exitosa", MessageBoxButtons.OK, MessageBoxIcon.Information);
            }
            catch (Exception ex)
            {
                MessageBox.Show("Error al conectar al puerto serial: " + ex.Message, "Error de Conexión", MessageBoxButtons.OK, MessageBoxIcon.Error);
            }
        }

        private void btnDesconectar_Click(object sender, EventArgs e)
        {
            if (puertoSerial != null && puertoSerial.IsOpen)
            {
                puertoSerial.Close();
                MessageBox.Show("Conexión cerrada correctamente.", "Desconexión Exitosa", MessageBoxButtons.OK, MessageBoxIcon.Information);
            }
        }

        private void btnReset_Click(object sender, EventArgs e)
        {
            txtBoxMensaje.Clear();
        }

        private void btnEnviar_Click(object sender, EventArgs e)
        {
            if (puertoSerial != null && puertoSerial.IsOpen)
            {
                puertoSerial.Write(txtBoxMensaje.Text);
            }
            else
            {
                MessageBox.Show("No hay una conexión activa con el puerto serial.", "Error de Envío", MessageBoxButtons.OK, MessageBoxIcon.Error);
            }
        }
    }
}
```
![imagen](https://i.imgur.com/0Gnnlvl.png)
