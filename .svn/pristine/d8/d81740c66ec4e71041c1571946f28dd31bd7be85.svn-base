package com.onsitesupport.controller;

import java.util.List;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.servlet.ModelAndView;

import com.onsitesupport.dao.PizzaDAO;
import com.onsitesupport.domain.Pizza;

@Controller("PizzaController")
public class PizzaController {
   
  @Autowired private PizzaDAO pizzaDAO;
   
  /**
   * This handler method is invoked when
   * http://localhost:8080/pizzashop is requested.
   * The method returns view name "index"
   * which will be resolved into /WEB-INF/index.jsp.
   *  See src/main/webapp/WEB-INF/servlet-context.xml
   */
  @RequestMapping("/list")
  public ModelAndView list() {
	  ModelAndView mav = new ModelAndView();
	  
	  List<Pizza> pizzas = pizzaDAO.findAll();
	  mav.addObject("pizzas", pizzas);
	  mav.setViewName("/pages/list");
    return mav;
  }
}
