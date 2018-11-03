/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package com.dao;

import com.model.Student; 
import java.util.List; 
import javax.ejb.Local; 

/**
 *
 * @author USER
 */
@Local
public interface StudentDAOLocal {
   void addStudent(Student student);
    void editStudent(Student student); 
    void deleteStudent(int studentId); 
    Student getStudent(int studentId); 
    List<Student> getAllStudents(); 
}

