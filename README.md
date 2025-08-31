    public sealed record Workplace(string Company, string Position);

    public interface IAbout
    {
        Workplace CurrentWorkplace { get; }
        IReadOnlyList<string> DailyKnowledge { get; }
        string FutureGoal { get; }
        string ToJson();
    }

    public sealed class About : Me, IAbout
    {
        public Workplace CurrentWorkplace { get; } = new("Rise Technology, Consulting & Academy", "Software Engineer");

        public IReadOnlyList<string> DailyKnowledge { get; } = new[]
        {
            ".NET",
            "ASP.NET Core",
            "C#",
            "Entity Framework Core",
            "REST & gRPC",
            "SQL Server",
            "PostgreSQL",
            "Redis",
            "Azure Service Bus",
            "Apache Kafka",
            "Docker",
            "Kubernetes (AKS)",
            "Azure API Management",
            "Azure DevOps (CI/CD)",
            "Terraform",
            "OpenTelemetry",
            "Serilog + ELK",
            "Prometheus + Grafana"
        };

        public string FutureGoal { get; } = "To contribute to open source.";

        public string ToJson() =>
            JsonSerializer.Serialize(new
            {
                workplace = new
                {
                    company = CurrentWorkplace.Company,
                    position = CurrentWorkplace.Position
                },
                dailyKnowledge = DailyKnowledge,
                futureGoal = FutureGoal
            }, new JsonSerializerOptions { WriteIndented = true });
    }
