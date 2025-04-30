package graphic;
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class StudentRegistrationForm extends JFrame implements ActionListener {
    private JTextField nameField, emailField, phoneField, classField;
    private JComboBox<String> genderBox;
    private JButton registerButton;
    private JLabel messageLabel;

    public StudentRegistrationForm() {
        setTitle("Оюутны бүртгэлийн форм");
        setSize(400, 350);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new GridBagLayout());
        setLocationRelativeTo(null);
        setLocation(0, 0);

        GridBagConstraints gbc = new GridBagConstraints();
        gbc.insets = new Insets(5, 5, 5, 5);
        gbc.fill = GridBagConstraints.HORIZONTAL;

        gbc.gridx = 0;
        gbc.gridy = 0;
        add(new JLabel("Оюутны нэр:"), gbc);

        gbc.gridx = 1;
        nameField = new JTextField(20);
        add(nameField, gbc);

        gbc.gridx = 0;
        gbc.gridy = 1;
        add(new JLabel("Имэйл хаяг:"), gbc);

        gbc.gridx = 1;
        emailField = new JTextField(20);
        add(emailField, gbc);

        gbc.gridx = 0;
        gbc.gridy = 2;
        add(new JLabel("Утасны дугаар:"), gbc);

        gbc.gridx = 1;
        phoneField = new JTextField(20);
        add(phoneField, gbc);

        gbc.gridx = 0;
        gbc.gridy = 3;
        add(new JLabel("Анги:"), gbc);

        gbc.gridx = 1;
        classField = new JTextField(20);
        add(classField, gbc);

        gbc.gridx = 0;
        gbc.gridy = 4;
        add(new JLabel("Хүйс:"), gbc);

        gbc.gridx = 1;
        String[] genders = {"Эрэгтэй", "Эмэгтэй", "Бусад"};
        genderBox = new JComboBox<>(genders);
        add(genderBox, gbc);

        gbc.gridx = 0;
        gbc.gridy = 5;
        gbc.gridwidth = 2;
        gbc.anchor = GridBagConstraints.CENTER;
        registerButton = new JButton("Бүртгүүлэх");
        registerButton.setContentAreaFilled(false);
        registerButton.addActionListener(this);
        add(registerButton, gbc);

        gbc.gridy = 6;
        messageLabel = new JLabel("", SwingConstants.CENTER);
        add(messageLabel, gbc);

        setVisible(true);
    }

    @Override
    public void actionPerformed(ActionEvent e) {
        String name = nameField.getText();
        String email = emailField.getText();
        String phone = phoneField.getText();
        String studentClass = classField.getText();
        String gender = (String) genderBox.getSelectedItem();

        if (name.isEmpty() || email.isEmpty() || phone.isEmpty() || studentClass.isEmpty()) {
            messageLabel.setText("Бүх талбарыг бөглөнө үү!");
        } else {
            messageLabel.setText("Амжилттай бүртгэгдлээ!");
            JOptionPane.showMessageDialog(this, "Оюутан: " + name + "\nИмэйл: " + email + "\nУтас: " + phone + "\nАнги: " + studentClass + "\nХүйс: " + gender);
        }
    }

    public static void main(String[] args) {
        new StudentRegistrationForm();
    }
} nadad iim student registration form baigaa
