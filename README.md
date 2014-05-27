package vistas;

import java.awt.BorderLayout;
import java.awt.Color;
import java.awt.FlowLayout;
import java.awt.GridLayout;

import javax.swing.Icon;
import javax.swing.ImageIcon;
import javax.swing.JButton;
import javax.swing.JDialog;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JPasswordField;
import javax.swing.JTextField;
import javax.swing.border.LineBorder;

import controladores.controladorVistaUsuario;



@SuppressWarnings("serial")
public class VistaUsuario extends JDialog {

	private JLabel lblApellidos,lblNombres,lblLogin,lblClave, lblMonto, lblIva, lblEdad, lblAdulto, lblDescuento;
	public JTextField txtApellidos,txtNombres,txtLogin, txtMonto, txtIva, txtEdad, txtAdulto, txtDescuento;
	public JPasswordField txtClave;
	public JButton btnRetornar,btnGuardar,btnModificar,
			btnVaciar,btnBuscar,btnEliminar, btnCalcular;
	public JPanel panelNorte,panelSur,panel,panel2,caja;
	public String ruta="E:/Descargas/src(3)/src/imagenes/";
	public VistaUsuario(){
		Icon iconoBuscar=new ImageIcon(ruta+"buscar.png");
		Icon iconoRetornar=new ImageIcon(ruta+"retornar.png");
		Icon iconoGuardar=new ImageIcon(ruta+"guardar.png");
		Icon iconoVaciar=new ImageIcon(ruta+"vaciar.png");
		Icon iconoModificar=new ImageIcon(ruta+"ingresar.png");
		Icon iconoEliminar=new ImageIcon(ruta+"papelera.png");
		Icon iconoCalcular=new ImageIcon(ruta+"iconos/32x32/bank.png");
		
		
		btnBuscar=new JButton(iconoBuscar);
		btnBuscar.setToolTipText("Buscar usuario  por login");
		
		btnRetornar=new JButton(iconoRetornar);
		btnRetornar.setToolTipText("Volver al Menu Principal");
		
		btnVaciar=new JButton(iconoVaciar);
		btnVaciar.setToolTipText("Borrar los campos del Formulario");
		
		btnGuardar=new JButton(iconoGuardar);
		btnGuardar.setToolTipText("Almacenar registro de Usuario");
		
		btnModificar=new JButton(iconoModificar);
		btnModificar.setToolTipText("Modificar datos del Usuario");
		
		btnEliminar=new JButton(iconoEliminar);
		btnEliminar.setToolTipText("Eliminar Usuario");
		
		btnCalcular=new JButton(iconoCalcular);
		btnCalcular.setToolTipText("Calcular Iva");
		
		lblApellidos=new JLabel("Apellidos:");
		txtApellidos=new JTextField(20);
		//txtApellidos.setEditable(false);
		lblNombres=new JLabel("Nombres:");
		txtNombres=new JTextField(20);
		
		lblLogin=new JLabel("Login:");
		txtLogin=new JTextField(10);
		
		lblClave=new JLabel("Clave:");
		txtClave=new JPasswordField(10);
		
		lblMonto=new JLabel("Ingrese Monto");
		txtMonto=new JTextField(6);
		
		lblIva=new JLabel("Iva");
		txtIva=new JTextField(6);
		txtIva.setEditable(false);
		
		lblEdad=new JLabel("Edad");
		txtEdad=new JTextField(3);
		
		lblAdulto=new JLabel("Adulto");
		txtAdulto= new JTextField(2);
		txtAdulto.setEditable(false);
		
		lblDescuento=new JLabel("Descuento");
		txtDescuento=new JTextField(6);
		txtDescuento.setEditable(false);
		
		panelNorte=new JPanel(new GridLayout(6,2));
		 
		 //---------> agregando al panel norte <----------
		 panel=new JPanel(new FlowLayout(FlowLayout.LEFT));
			 
		 panel.add(lblLogin);
		 panel.add(txtLogin); 
		 panel.add(btnBuscar);
		 panelNorte.add(panel);

		 panel=new JPanel(new FlowLayout(FlowLayout.LEFT));
		 
		 panel.add(lblClave);
		 panel.add(txtClave); 
		 panelNorte.add(panel);
		 
		 panel=new JPanel(new FlowLayout(FlowLayout.LEFT));
		 
		 panel.add(lblApellidos);
		 panel.add(txtApellidos); 
		 panelNorte.add(panel);
		 
		 panel=new JPanel(new FlowLayout(FlowLayout.LEFT));
		 
		 panel.add(lblNombres);
		 panel.add(txtNombres); 
		 panelNorte.add(panel);
		 
		 panel=new JPanel(new FlowLayout(FlowLayout.LEFT));
		 
		 panel.add(lblEdad);
		 panel.add(txtEdad);
		 panel.add(lblAdulto);
		 panel.add(txtAdulto);
		 panelNorte.add(panel);
		 
		 panel=new JPanel(new FlowLayout(FlowLayout.LEFT));
		 
		 panel.add(lblMonto);
		 panel.add(txtMonto);
		 panel.add(lblDescuento);
		 panel.add(txtDescuento);
		 panel.add(lblIva);
		 panel.add(txtIva);
		 panelNorte.add(panel);
		 
		 panelSur=new JPanel(new GridLayout(1,6));
			
		 panelSur.add(btnCalcular);
		 panelSur.add(btnGuardar);
		 panelSur.add(btnModificar);
		 panelSur.add(btnEliminar);
		 panelSur.add(btnVaciar);
		 panelSur.add(btnRetornar);
		
		 caja=new JPanel(new BorderLayout());
		 caja.add(panelNorte,BorderLayout.NORTH);
		 caja.add(panelSur,BorderLayout.SOUTH);
		 caja.setBorder(new LineBorder(Color.BLUE,4,true));
		 this.add(caja);
		
		//---------->acciones <---------
		 
		 controladorVistaUsuario eco=new controladorVistaUsuario(this);
		 
		 btnRetornar.addActionListener(eco);
		 btnVaciar.addActionListener(eco);
		 btnCalcular.addActionListener(eco);
		 txtLogin.addKeyListener(eco);
		 txtClave.addKeyListener(eco);
		 txtApellidos.addKeyListener(eco);
		 txtNombres.addKeyListener(eco);
		 txtMonto.addKeyListener(eco);
		 txtEdad.addKeyListener(eco);
		 
		this.addWindowListener(eco);
	
		//this.setUndecorated(true);
		 setSize(500,350);
			
		 this.setLocationRelativeTo(null);
		 this.pack();
		 this.setAlwaysOnTop(true);
			
		 setVisible(true);
		 
		
	}
	
	public static void main(String[] args) {
		new VistaUsuario();

	}

}

