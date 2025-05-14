import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent; 
import java.awt.event.ActionListener; 
import java.util.ArrayList;
class Patient {
private String name; private int age; private String gender;
private String healthIssue;
public Patient(String name, int age, String gender, String healthIssue) { this.name = name;
this.age = age; this.gender = gender;
this.healthIssue = healthIssue;
}
public String toString() {
return "Name: " + name + ", Age: " + age + ", Gender: " + gender + ", Health Issue: " + healthIssue;
}
}
public class PatientRegistryManagementSystem extends JFrame { private ArrayList<Patient> patientList;
private JTextField nameField, ageField, healthIssueField; private JComboBox<String> genderComboBox;
private JTextArea patientTextArea;
public PatientRegistryManagementSystem() { setTitle("Patient Registry Management System"); setSize(500, 400); setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); setLocationRelativeTo(null);
patientList = new ArrayList<>(); JPanel mainPanel = new JPanel();
mainPanel.setLayout(new BorderLayout());
JPanel inputPanel = new JPanel(new GridBagLayout()); GridBagConstraints gbc = new GridBagConstraints(); gbc.insets = new Insets(5, 5, 5, 5);
nameField = new JTextField(20); ageField = new JTextField(20); healthIssueField = new JTextField(20);
genderComboBox = new JComboBox<>(new String[]{"Male", "Female", "Other"}); gbc.gridx = 0;
gbc.gridy = 0;
inputPanel.add(new JLabel("Name:"), gbc);
gbc.gridx = 1;
gbc.gridy = 0; inputPanel.add(nameField, gbc);
gbc.gridx = 0;
gbc.gridy = 1;
inputPanel.add(new JLabel("Age:"), gbc);
gbc.gridx = 1;
gbc.gridy = 1; inputPanel.add(ageField, gbc);
gbc.gridx = 0;
gbc.gridy = 2;
inputPanel.add(new JLabel("Gender:"), gbc);
gbc.gridx = 1;
gbc.gridy = 2; inputPanel.add(genderComboBox, gbc);
gbc.gridx = 0;
gbc.gridy = 3;
inputPanel.add(new JLabel("Health Issue:"), gbc);
gbc.gridx = 1;
gbc.gridy = 3; inputPanel.add(healthIssueField, gbc);
JButton addButton = new JButton("Add Patient"); addButton.addActionListener(new ActionListener() {
public void actionPerformed(ActionEvent e) { addPatient();
}
});
gbc.gridx = 1;
gbc.gridy = 4;
gbc.anchor = GridBagConstraints.LINE_END; inputPanel.add(addButton, gbc);
mainPanel.add(inputPanel, BorderLayout.NORTH);
patientTextArea = new JTextArea(15, 40); patientTextArea.setEditable(false);
mainPanel.add(new JScrollPane(patientTextArea), BorderLayout.CENTER);
add(mainPanel);
}
private void addPatient() {
String name = nameField.getText();
int age = Integer.parseInt(ageField.getText());
String gender = (String) genderComboBox.getSelectedItem(); String healthIssue = healthIssueField.getText();
Patient newPatient = new Patient(name, age, gender, healthIssue); patientList.add(newPatient);
updatePatientList();
}
private void updatePatientList() {
StringBuilder patientListText = new StringBuilder(); for (Patient patient : patientList) {
patientListText.append(patient.toString()).append("\n");
}
patientTextArea.setText(patientListText.toString());
}
public static void main(String[] args) { SwingUtilities.invokeLater(() -> {
PatientRegistryManagementSystem system = new PatientRegistryManagementSystem();
system.setVisible(true);
});
}
}
