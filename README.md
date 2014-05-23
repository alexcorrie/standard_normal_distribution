# standard_normal_distribution
# ============================

# R Code for Standard Normal Distribution Graphic with Shaded Regions

# Standard Normal Probability Distribution with Shaded Regions
par(mar = c(5.2, 7.2, 4.2, 2.2))
curve(dnorm(x, mean = 0 , sd = 1), xlim = c(-3.25, 3.25), ylim = c(0, 0.42),
      main = "Standard Normal Distribution", 
      xlab = "Z", ylab = expression(P(Z)==(1/sqrt(2*pi))*e^(-(Z^2)/2)), 
      cex = 0.5, frame.plot = FALSE)
text(0, dnorm(0) + 0.015, expression(mu==0), adj = 0)

    # Boundaries with text for P(Z) integral (using dnorm) from a to b
x.val <- c(-3, seq(-3, -2, 0.01), -2)
y.val <- c(0, dnorm(seq(-3, -2, 0.01)), 0)
polygon(x.val, y.val, col = "skyblue")
text(-2.5, dnorm(-2.5) + 0.03, round(pnorm(-2) - pnorm(-3), 4), adj = 0.5)

x.val.2 <- c(-2, seq(-2, -1, 0.01), -1)
y.val.2 <- c(0, dnorm(seq(-2, -1, 0.01)), 0)
polygon(x.val.2, y.val.2, col = "lightyellow")
text(-1.5, dnorm(-2.5) + 0.05, round(pnorm(-1) - pnorm(-2), 4), adj = 0.5)

x.val.3 <- c(-1, seq(-1, 0, 0.01), 0)
y.val.3 <- c(0, dnorm(seq(-1, 0, 0.01)), 0)
polygon(x.val.3, y.val.3, col = "lightgreen")
text(-0.5, dnorm(-2.5) + 0.08, round(pnorm(0) - pnorm(-1), 4), adj = 0.5)

x.val.4 <- c(0, seq(0, 1, 0.01), 1)
y.val.4 <- c(0, dnorm(seq(0, 1, 0.01)), 0)
polygon(x.val.4, y.val.4, col = "lightgreen")
text(0.5, dnorm(2.5) + 0.08, round(pnorm(1) - pnorm(0), 4), adj = 0.5)

x.val.5 <- c(1, seq(1, 2, 0.01), 2)
y.val.5 <- c(0, dnorm(seq(1, 2, 0.01)), 0)
polygon(x.val.5, y.val.5, col = "lightyellow")
text(1.5, dnorm(2.5) + 0.05, round(pnorm(2) - pnorm(1), 4), adj = 0.5)

x.val.6 <- c(2, seq(2, 3, 0.01), 3)
y.val.6 <- c(0, dnorm(seq(2, 3, 0.01)), 0)
polygon(x.val.6, y.val.6, col = "skyblue")
text(2.5, dnorm(2.5) + 0.03, round(pnorm(3) - pnorm(2), 4), adj = 0.5)

text(-3.1, 0.02, round(pnorm(-3), 4), adj = 1)
text(3.1, 0.02, round(1 - pnorm(3), 4), adj = 0)
